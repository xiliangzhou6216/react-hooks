---
title: user-media
nav:
  title: Hooks
  path: /hook
---

# user-media

Open a media stream in browser to produce video and audio from client.

```shell
npm install @huse/user-media
```

## useUserMedia

This hook tries to open a media stream via its `constraints` argument, returning a context indicating current streaming state, see [getUserMedia](https://developer.mozilla.org/en-US/docs/Web/API/MediaDevices/getUserMedia) to understand its underlying browser capabilities.

```typescript
interface UserMediaHook {
    stream: MediaStream | null;
    recording: boolean;
    error: Error | null;
    start: () => void;
    stop: () => void;
}

function useUserMedia(
    constraints?: MediaStreamConstraints,
    onSuccess?: (stream: MediaStream) => void,
    onError?: (error: Error) => void
): UserMediaHook;
```

By default `useUserMedia` requires both video and audio channels.

**NOTE: On a browser where `getUserMedia` is not implemented, this hooks returns `UserMediaHook` object with a special `error` containing `code` property of `"ERR_METHOD_NOT_IMPLEMENTED"`.**

<code src='./demo/useUserMedia.tsx'>
