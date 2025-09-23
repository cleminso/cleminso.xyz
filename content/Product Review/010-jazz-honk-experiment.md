---
title: "010 - Jazz-honk Experiment"
date: 2025-09-23T00:00:00
weight: 990
draft: false
description: Jazz-honk is a real-time messaging experience inspired by Honk.
tags:
  - Jazz
  - My Project
ShowBreadCrumbs: true
---

I made a small experiment over this weekend - [Jazz-Honk](https://jazz-honk.vercel.app). I’m writing this blog post to share how I built it based on [Jazz chat app](https://github.com/garden-co/jazz/tree/main/examples/chat) example.

A few months ago, I read Benji’s [blog post](https://benji.org/honkish) about small interactions and playful details about Honk app, now sunsetted 2 years ago.

Honk was a real-time messaging app, with two vertical chat bubbles, no send button, no chat history, and no drafts. Every character appears instantly on participants screens and bubbles layout change based on typing state.

Since Jazz handles real-time sync perfectly, this was a perfect experiment to replicate. The trickiest part was implementing the bubble behavior, especially on mobile.

---

## Schema Structure

With Jazz we first define our [entity schema](https://github.com/cleminso/jazz-experiments/blob/main/examples/jazz-honk/src/schema.ts). For a basic messaging app we simply need a ChatRoom entity as `co.map()` - enabling real-time sync of the shared ChatRoom state.

`ChatRoom` contains the bubbles and ownership fields. Using `bubble: co.plainText(),` enable user text editing.

Since we need frequent text edits,`co.plaintext()` gives more control than a static`z.string()` that only syncs when the entire value changes. As each participant types, others see the text appear character by character.

To persist the identity, each user gets assigned to a specific bubble and each field needs independent sync. This prevents users from editing the same bubble.

```typescript
export const ChatRoom = co.map({
  bubble1: co.plainText(),
  bubble2: co.plainText(),
  bubble1Owner: z.optional(z.string()),
  bubble2Owner: z.optional(z.string()),
});
```

`BubbleOwner` is `z.optional` because when a chat room is first created, no one owns any bubbles yet. The chat creator gets assigned to `bubble1Owner`, then the second user get assigned to the remaining `bubble2Owner`.

Without optional Owner new ChatRoom would require owners to be set upfront. Attempting to access undefined owners would crash the app.

Then we use `z.string()` to store the user Jazz AccountID, we get from: `const userId = user.$jazz.id;`. This allows tracking which user owns which bubble.

---

## Frontend Implementation

Defining `co.plainText()` for bubbles enables:

1. UI detects when user is typing by watching content changes

2. bubble behavior (grow/shrink) based on the user typing

So in [`chatScreen.tsx`](https://github.com/cleminso/jazz-experiments/blob/main/examples/jazz-honk/src/chatScreen.tsx):

```typescript
const handleMyBubbleChange = (text: string) => {
  myBubble?.$jazz.applyDiff(text);
};
```

Here `handleMyBubbleChange` takes the user's input and applies it through `myBubble?.$jazz.applyDiff(text)`. Rather than overwriting the entire text, `applyDiff` sends only the changes to other users. As you type "Hello", other users see "H", then "He", then "Hel", character by character, all sync through Jazz’s network.

**How the user identify is handles?**

1. When the user first open the app, a Jazz AccountID is generated and get a random profile name:

```typescript
const defaultProfileName = url.searchParams.get("user") ?? getRandomUsername();

// In app.tsx - this triggers account creation
<JazzReactProvider
  sync={{ peer: `wss://cloud.jazz.tools/?key=${apiKey}` }}
  defaultProfileName={defaultProfileName}
>
```

2.  Users can change their profile name:

```typescript
// From chatScreen.tsx
me.profile.$jazz.set("name", e.target.value);
```

3. Other users see profile name:

```typescript
// From ui.tsx - automatically syncs
const otherUser = useCoState(Account, otherUserId);
{
  otherUser?.profile?.name || "Anonymous";
}
```

Using `useCoState` enables to subscribe to a given CoValue and detect changes. In our case the other user `Account` with us in the chatRoom. It automatically re-renders the react component when data changes and propagates the change.

To simplify the experience, I leverage Anonymous option provided by Jazz. User identity is tied to the browser session, this means:

- Refresh the page → Same identity, rejoin the same bubble

- New browser/incognito → New identity, might join as 2nd user

- Clear browser data → Lose your identity, become a new user and can start a new chat

---

## Thoughts

Voilà, it's a really simple proof-of-concept that I feel represents a better way to showcase Jazz's real-time possibilities through a messaging interface.

To keep the experiment simple, there are no access permissions to the chatRoom - that would require more complex logic with user authentication and identity management. Just share the chatRoom URL to invite someone.

I was surprised that "simple" app examples aren't necessarily the simplest to build. While not that complex, it required really precise implementation.
