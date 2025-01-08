# C Memory Allocation and Copying Bug

This repository demonstrates a common error in C programming involving memory allocation and copying of arrays using `malloc` and `memcpy`. The code allocates memory dynamically, copies data from a static array, and then frees the allocated memory.

## The Bug

The primary issue lies in the use of `sizeof(arr)` within the `memcpy` function.  `sizeof(arr)` returns the size of the array in bytes, which is determined at compile time. If the size of `arr` changes, `memcpy` might not copy the entire updated array, leading to incomplete data copying.  Furthermore, error handling for `malloc` failure is crucial and is missing.