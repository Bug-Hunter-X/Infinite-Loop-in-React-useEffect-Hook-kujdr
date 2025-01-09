# React useEffect Infinite Loop Bug

This repository demonstrates a common bug in React applications involving the `useEffect` hook.  The bug causes an infinite loop due to a missing dependency in the `useEffect` dependency array.

## Bug Description
The `MyComponent` component uses `useState` to track a count. The `useEffect` hook is intended to log the current count and perform cleanup when the component unmounts. However, because `count` is missing from the dependency array, the effect runs after every render, triggering a state update and leading to an infinite loop.

## How to Reproduce
1. Clone this repository.
2. Run `npm install`.
3. Run `npm start`.
4. Observe the infinite loop in your browser's console and the continuously updating counter on the screen.

## Solution
The solution involves adding `count` to the dependency array of the `useEffect` hook.  This ensures the effect only runs when the value of `count` changes.