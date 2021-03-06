---
title: scroll-position
nav:
  title: Hooks
  path: /hook
---

# scroll-position

Provides a set of hooks to observe element or window scroll position.

```shell
npm install @huse/scroll-position
```

## useScrollPosition

Observe and returns scroll position of an element or window.

```typescript
interface ScrollPosition {
    x: number;
    y: number;
    left: number;
    top: number;
    scrollLeft: number;
    scrollTop: number;
}

function useScrollPosition(element?: HTMLElement | null): ScrollPosition
```

**Note there are different behaviors when `element` is either `null` or `undefined`, commonly `useRef`'s initial value is `null`.**
When `documentElement` is the observe target, simple `useScrollPosition()` without argument.

In order to satisfy different developers, the returned `ScrollPosition` has a set of different key pairs,
all `x`, `left`, `scrollLeft` have same value while `y`, `top`, `scrollTop` have same value.

<code src='./demo/useScrollPosition.tsx'>

## useScrollLeft

`useScrollLeft` is a short hook to get the `left` value of `useScrollPosition`.

## useScrollTop

`useScrollTop` is a short hook to get the `top` value of `useScrollPosition`.
