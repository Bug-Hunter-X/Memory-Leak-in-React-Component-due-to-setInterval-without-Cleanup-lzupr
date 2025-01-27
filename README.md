## React Memory Leak: setInterval without Cleanup

This repository demonstrates a common error in React components: using `setInterval` within `useEffect` without a cleanup function. This can lead to memory leaks and unexpected behavior.

The `bug.js` file contains the faulty component, while `bugSolution.js` provides the corrected version.

**Problem:**
The `setInterval` function continues to run even after the component is unmounted, causing a memory leak.  The component keeps updating the count even though it is not rendered anymore.

**Solution:**
The `useEffect` hook's return value is used to specify a cleanup function, which is called before the component is unmounted. This function clears the interval, preventing memory leaks.