# React useEffect setInterval Memory Leak

This repository demonstrates a common bug in React applications involving the use of `setInterval` within the `useEffect` hook.  The bug leads to a memory leak because the interval is not properly cleared when the component unmounts.

## Bug Description

The `MyComponent` uses `setInterval` to update a counter every second.  However, it fails to include a cleanup function in the `useEffect` hook's return statement to clear the interval using `clearInterval`. This results in the interval continuing to run even after the component is unmounted, leading to a memory leak.

## Solution

The solution involves adding a cleanup function to the `useEffect` hook that clears the interval using `clearInterval` before the component is unmounted. This ensures that the interval is stopped, preventing the memory leak.