# React Router DOM Catch-all Route Conflict

This repository demonstrates a subtle bug in React Router DOM v6 related to the interaction between catch-all routes ("/*") and nested routes.  The catch-all route incorrectly activates even when a more specific route should match.

## Issue Description

The provided `App.js` demonstrates the problem.  Even when navigating to routes like `/about`, the `NotFound` component (representing the catch-all route) is rendered.  This shouldn't occur as the `/about` route should take precedence.

## Solution

The solution involves using `useLocation` hook to accurately determine the path and render the `NotFound` component accordingly, ensuring that it only shows when no other routes match.