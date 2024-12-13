# React Memory Leak: setInterval in useEffect without Cleanup

This repository demonstrates a common React memory leak caused by improper usage of the `setInterval` function within the `useEffect` hook.  The problem arises from the lack of a cleanup function to stop the interval when the component unmounts.  This leads to the interval continuing indefinitely, consuming resources even after the component is no longer needed.

The `bug.js` file shows the problematic code, while `bugSolution.js` provides the corrected version.

## How to reproduce

1. Clone the repository.
2. Run `npm install`.
3. Run `npm start`.
4. Observe the increasing counter.  The memory leak will not be directly apparent, but it will cause performance issues over time if not fixed.

## Solution

The solution involves using the return value of `useEffect` to add a cleanup function. This function will clear the interval when the component unmounts, preventing the memory leak.