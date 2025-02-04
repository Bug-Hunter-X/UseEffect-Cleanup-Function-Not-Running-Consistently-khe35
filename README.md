# React useEffect Cleanup Function Issue

This repository demonstrates a problem with the cleanup function in React's `useEffect` hook.  The expected behavior is for the cleanup function to execute before the effect runs again, allowing for resource cleanup (e.g., event listeners, timers, etc.). However, in this specific example, the cleanup function does not always behave as expected.

## Problem Description

The `useEffect` hook is used to perform side effects. The cleanup function, returned from `useEffect`, should be called before the next effect runs or before the component unmounts.  In this case, the cleanup function logs 'Cleanup' to the console.  However, this message is not always logged before the next 'Count' log, indicating inconsistent execution of the cleanup function.

## How to Reproduce

1. Clone the repository.
2. Run `npm install` to install dependencies.
3. Run `npm start` to start the development server.
4. Observe the console logs.  You'll notice that the 'Cleanup' message is not always printed before the next 'Count' message.

## Solution

The solution involves a subtle adjustment to the effect's dependency array.  Refer to `bugSolution.js` for the corrected code.