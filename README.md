# Next.js 15 Navigation Bug in Conditionally Rendered Components

This repository demonstrates a bug in Next.js 15 where using `next/navigation` client-side routing within a conditionally rendered component can lead to an uninitialized router object.  This results in errors when attempting to use navigation functions like `router.push()`.

## Steps to Reproduce

1. Clone this repository.
2. Run `npm install`.
3. Run `npm run dev`.
4. Observe the error when navigating.  The error is only present on the client-side when the conditional rendering is in place, making it tricky to debug.

## Solution

The solution involves ensuring the router is properly initialized before attempting navigation. This can be achieved using techniques like `useEffect` with a dependency array to only execute the navigation function when the component is mounted and the required conditions are met.