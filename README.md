# React setInterval Memory Leak
This repository demonstrates a common error in React applications: using `setInterval` within the `useEffect` hook without proper cleanup. This leads to memory leaks because the interval continues to run even after the component unmounts.

## Bug
The `bug.js` file contains a React component that uses `setInterval` to update a counter every second. However, it fails to include a cleanup function within the `useEffect` hook to clear the interval when the component is unmounted.

## Solution
The `bugSolution.js` file provides the corrected code.  It uses the return value of the `useEffect` hook to clear the interval using `clearInterval` before the component is unmounted, preventing memory leaks.

## How to reproduce
Clone this repository and run `npm install` to install the dependencies. Then you can run `npm start` to start a development server. You'll see the memory leak in the browser's developer tools if you don't correctly clear the `setInterval`.