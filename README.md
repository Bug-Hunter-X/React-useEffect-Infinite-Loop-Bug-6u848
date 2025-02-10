# React useEffect Infinite Loop Bug

This repository demonstrates a common error in React's `useEffect` hook:  forgetting to include dependencies in the dependency array. This leads to an infinite loop and unexpected behavior.

## Bug Description
The `useEffect` hook in `bug.js` is intended to log the current count to the console after each update. However, because the dependency array `[count]` is omitted, the effect runs after every render, regardless of changes to the count. This causes an infinite loop because updating the count triggers a re-render, which again triggers the effect, and so on.

## Solution
The corrected code in `bugSolution.js` includes the `count` variable in the dependency array. This ensures that the effect only runs when the value of `count` changes.