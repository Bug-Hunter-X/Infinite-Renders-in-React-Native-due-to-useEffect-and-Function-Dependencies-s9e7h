# React Native useEffect Hook with Function Dependency Issue

This repository demonstrates a common but subtle bug in React Native applications involving the `useEffect` hook and its dependency array.  The problem arises when a function is included as a dependency, leading to unintended re-renders and potentially infinite loops.  The solution involves using `useCallback` to memoize the function, ensuring it only changes when its dependencies change.

## Problem

The `bug.js` file shows an example of the incorrect usage of `useEffect` with a function dependency.  The `myFunction` is recreated on every render, triggering the `useEffect` hook repeatedly, resulting in infinite rerenders. 

## Solution

The `bugSolution.js` file presents a corrected version utilizing `useCallback` to memoize the function.  `useCallback` returns a memoized version of the callback that only changes if one of the dependencies has changed.  This prevents unnecessary re-renders and resolves the infinite loop issue.

## How to Reproduce

1. Clone the repository
2. Run `npm install`
3. Run the application using your preferred React Native method
4. Observe the console output for the infinite renders in the `bug.js` example
5. Compare the console output of the corrected version in `bugSolution.js`