# React 18 useEffect setInterval Memory Leak and Unexpected Batching

This repository demonstrates a common issue in React 18 involving `setInterval` within a `useEffect` hook. The improper cleanup of the interval leads to memory leaks, and the automatic batching introduced in React 18 can cause the counter updates to behave unexpectedly.

## Bug
The `bug.js` file contains a component that uses `setInterval` to update a counter.  However, it fails to clean up the interval when the component unmounts, resulting in a memory leak.  Furthermore, React 18's automatic batching may cause the counter updates to be less frequent than expected.

## Solution
The `bugSolution.js` file demonstrates the correct way to use `setInterval` within a `useEffect` hook. It includes a cleanup function that clears the interval when the component unmounts, preventing memory leaks.  