# Express.js Route Handler Missing Error Handling for Invalid User ID

This repository demonstrates a common error in Express.js route handlers:  missing error handling for invalid input.  Specifically, the example shows a route that fetches a user by ID.  If the ID is not a valid number, the code will throw an error.

The `bug.js` file contains the erroneous code.  The `bugSolution.js` file provides a corrected version with appropriate error handling.

## Bug

The bug lies in the lack of input validation.  The route handler attempts to parse the `userId` as an integer using `parseInt()` without checking if the input is actually a number. If a non-numeric ID is passed, `parseInt()` will return `NaN`, leading to a potential crash or unexpected behavior.

## Solution

The solution involves adding input validation to check if the `userId` is a number before attempting to parse it.  If it's not a number, a 400 Bad Request response should be sent to the client, indicating that the input is invalid.  Additional checks for null or undefined values are also beneficial.