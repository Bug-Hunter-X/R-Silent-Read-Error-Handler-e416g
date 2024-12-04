# Silent File Reading Failure in R

This repository demonstrates a common, yet easily missed, error in R: silent failure when attempting to read a file that doesn't exist.  The provided `bug.R` script uses `tryCatch` to handle potential errors during file reading, but the error handling is inadequate, leading to the program continuing execution without any indication of failure.  The solution (`bugSolution.R`) provides a more robust approach.

## Problem

The `bug.R` script attempts to read a CSV file. If the file is not found, the `tryCatch` block catches the error, but it doesn't provide any useful feedback, leaving the user unaware of the problem.  This can be particularly problematic in larger, more complex scripts where the cause of subsequent errors might be difficult to trace back to the initial file reading failure. 

## Solution

The `bugSolution.R` script improves error handling. It explicitly checks if the file exists before attempting to read it.  If the file doesn't exist, it generates a more informative error message, making debugging much easier.