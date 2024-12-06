# React useEffect Infinite Loop Bug

This repository demonstrates a common bug in React applications where the `useEffect` hook runs infinitely, even when a dependency array is provided.  This often occurs due to a misunderstanding of how `useEffect` interacts with state updates.

## Problem

The provided `MyComponent` uses `useEffect` to log the current count whenever the count changes. However, the effect itself causes the count to update, leading to an infinite loop. This is because the state update causes a re-render, which in turn triggers the effect again, leading to an endless cycle.

## Solution

The solution lies in carefully considering the dependencies passed to `useEffect`.  In this case, the effect should only run when the count is initially set or when the component mounts.