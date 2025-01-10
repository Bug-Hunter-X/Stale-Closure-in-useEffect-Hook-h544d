# Stale Closure Bug in React's useEffect Hook

This repository demonstrates a common bug in React applications involving the `useEffect` hook and stale closures. The bug arises when a dependency is not included in the dependency array, leading to unexpected behavior.

## Bug Description
The `MyComponent` component uses `useEffect` to update a counter every second.  However, the dependency array `[]` is empty.  This means the effect runs only once after the initial render.  The `count` variable inside the `setInterval` callback refers to the initial value of `count`, not the updated value. This results in the counter not incrementing correctly.

## Solution
The solution involves including the `count` variable in the dependency array to ensure the effect runs whenever `count` changes.