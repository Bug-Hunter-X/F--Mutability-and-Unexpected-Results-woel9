# F# Mutability Bug

This example demonstrates a common issue in F# related to mutability and unexpected results.  The code calculates the sum of two mutable variables, but the result is affected by changes made to the variables *after* the initial calculation.

## Problem
The program uses mutable variables (`let mutable`), and modifying these variables after the initial calculation changes the result in unexpected ways.

## Solution
The issue is resolved by using immutable values. Alternatively, the calculation can be explicitly repeated after the values are updated.

## How to reproduce
1. Compile the `bug.fs` file.
2. Run the compiled program and observe the output.  The first output should be 30, then 40.  This happens because the `add` function operates on the *current* values of `x` and `y` which are changing.