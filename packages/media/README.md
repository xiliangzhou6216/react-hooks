---
title: media
nav:
  title: Hooks
  path: /hook
---

# media

Provides hooks to observe media query matches.

```shell
npm install @huse/media
```

## useMedia

Observe the given media query and return whether it is satisfied by current environment.

```typescript
function useMedia(query: string): boolean;
```

The return value is responsive to viewport and device changes.

<code src="./demo/useMedia.tsx">

## usePreferDarkMode

A shortcut hook to determine whether current user prefers dark mode.

```typescript
function usePreferDarkMode(): boolean;
```

This hook is also response, that means the value will be updated if system changes color scheme or having a automatic scheme.

<code src="./demo/usePreferDarkMode.tsx">
