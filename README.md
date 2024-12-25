# React useEffect Hook Memory Leak

This repository demonstrates a common mistake in using the `useEffect` hook in React: forgetting to include a cleanup function to prevent memory leaks.  The example shows a component that uses `setInterval` to update a counter, but fails to clear the interval when the component is unmounted. This leads to the `setInterval` continuing to run, causing unnecessary updates and potential memory issues.

The `bug.js` file contains the buggy code, while `bugSolution.js` provides the corrected version with a proper cleanup function.

## Bug
The bug lies in the `useEffect` hook. It starts an interval but never stops it when the component unmounts.

## Solution
The solution is to return a cleanup function from the `useEffect` hook. This function is responsible for clearing the interval when the component unmounts, preventing memory leaks.

## How to reproduce
1. Clone this repository.
2. Run `npm install` to install the required packages.
3. Run `npm start` to start the development server.
4. Observe the counter in the browser.
5. Try navigating away from the page or refreshing the browser. The counter in the buggy version should still keep increasing