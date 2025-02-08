# React setInterval Memory Leak

This repository demonstrates a common error in React applications: using `setInterval` without properly cleaning up the interval when the component unmounts. This leads to memory leaks and potential performance issues.

## Bug Description

The `MyComponent` uses `setInterval` to update a counter every second.  However, it fails to store the interval ID returned by `setInterval` and clear it using `clearInterval` within a cleanup function in the `useEffect` hook.  This causes the interval to continue running even after the component is unmounted, leading to a memory leak.

## Solution

The solution involves storing the interval ID in a state variable and clearing the interval in the cleanup function of the `useEffect` hook.