# JavaScript Closure Issue with setTimeout

This repository demonstrates a common JavaScript closure issue that can occur when using `setTimeout` within a loop. The problem arises because the `setTimeout` callback function doesn't capture the value of `i` at the time it's created, but instead captures a reference to the variable `i`. By the time `setTimeout` finally executes, the loop has already completed, and `i` holds its final value.

## The Bug

The file `bug.js` contains the buggy code. When you run this code, you might expect to see the numbers 0 through 9 printed to the console with a one-second delay between each number.  Instead, you'll see the number 10 printed ten times.

## The Solution

The file `bugSolution.js` provides a corrected version of the code using an immediately invoked function expression (IIFE) to create a closure that captures the correct value of `i` for each iteration of the loop.  This solution ensures that the correct value is used when the `setTimeout` callback executes.

## How to Reproduce

1. Clone the repository.
2. Navigate to the directory containing `bug.js` and `bugSolution.js`.
3. Run the buggy code using Node.js: `node bug.js`
4. Run the corrected code using Node.js: `node bugSolution.js`

Observe the difference in output between the two versions.