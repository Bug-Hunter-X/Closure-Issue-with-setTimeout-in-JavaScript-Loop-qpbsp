# JavaScript Closure Issue with setTimeout in a Loop

This repository demonstrates a common JavaScript closure issue that can occur when using `setTimeout` within a loop.  The problem arises because the `setTimeout` callback function doesn't immediately execute; it's scheduled to run later. By that time, the loop variable `i` might have already changed its value.

## The Problem

The `bug.js` file contains a function `myFunction` that uses `setTimeout` to log the value of `i` after a 1-second delay. You might expect it to print 0 through 9. However, because of the closure issue, it prints 10 ten times, due to the asynchronous nature of `setTimeout`.

## The Solution

The `bugSolution.js` file provides a solution using an immediately invoked function expression (IIFE) to create a new scope for the loop variable `i`.  This ensures that each callback function has its own copy of the value of `i` at the time the `setTimeout` function is called, solving the closure problem.

## How to Run

1. Clone this repository.
2. Open `bug.js` and `bugSolution.js` in your preferred JavaScript environment.
3. Run each file to see the different outputs and understand the impact of the closure issue.