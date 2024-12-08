# Express.js Route Handler Missing Error Handling for Invalid User ID

This repository demonstrates a common error in Express.js route handlers: the lack of error handling for invalid input. Specifically, the code attempts to parse a user ID as an integer without checking if the input is valid, which can lead to unexpected errors.

## Bug

The `bug.js` file contains the erroneous code.  It attempts to find a user based on an ID passed as a route parameter. If the ID is not a valid integer, `parseInt` will return `NaN`, causing the `find` method to always return `undefined`. This will result in a `404` status, but other errors might occur depending on the rest of the application code.

## Solution

The `bugSolution.js` file provides a corrected version of the code. It includes explicit checks to ensure the user ID is a valid integer before attempting to find the user.  This prevents potential errors and improves the robustness of the application.

## How to reproduce

1. Clone this repository.
2. Navigate to the repository directory.
3. Run `npm install express`
4. Run `node bug.js` and then send a request to `/users/abc` to observe error.
5. Run `node bugSolution.js` and then send a request to `/users/abc` to see the improvement.