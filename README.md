# matrix-shell-scripts

## Overview

In this assignment, you will write a bash shell script that calculates basic matrix operations using input from either a file or stdin. The input will be whole number values separated by tabs into a rectangular matrix. Your script should be able to print the dimensions of a matrix, transpose a matrix, calculate the mean vector of a matrix, add two matrices, and multiply two matrices.

You will be using bash builtins and Unix utilities to complete the assignment.

Your script must be called simply "matrix". The general format of the matrix command is: matrix OPERATION [ARGUMENT]...

## Specifications

Your program must perform the following operations: dims, transpose, mean, add, and multiply. Usage is as follows:

matrix dims [MATRIX]
matrix transpose [MATRIX]
matrix mean [MATRIX]
matrix add MATRIX_LEFT MATRIX_RIGHT
matrix multiply MATRIX_LEFT MATRIX_RIGHT

dims should print the dimensions of the matrix as the number of rows, followed by a space, then the number of columns.
transpose should reflect the elements of the matrix along the main diagonal. Thus, an MxN matrix will become an NxM matrix and the values along the main diagonal will remain unchanged.
mean should take an MxN matrix and return an 1xN row vector, where the first element is the mean of column one, the second element is the mean of column two, and so on.
add should take two MxN matrices and add them together element-wise to produce an MxN matrix. add should return an error if the matrices do not have the same dimensions.
multiply should take an MxN and NxP matrix and produce an MxP matrix. Note that, unlike addition, matrix multiplication is not commutative. That is A*B != B*A.

You must check for the right number and format of arguments to matrix. This means that, for example, you must check that a given input file is readable, before attempting to read it. You are not required to test if the input file itself is valid. In other words, the behavior of matrix is undefined when the matrix input is not a valid matrix. for the purposes of this assignment, a valid matrix is a tab-delimited table containing at least one element, where each element is a signed integer, every entry is defined, and the table is rectangular.

The following are examples of invalid matrices:

An empty matrix.
A matrix where the final entry on a row is followed by a tab character.
A matrix with empty lines.
A matrix with any element that is blank or not an integer.

If the inputs are valid -- your program should output only to stdout, and nothing to stderr. The return value should be 0.

If the inputs are invalid -- your program should output only to stderr, and nothing to stdout. The return value should be any number except 0. The error message you print is up to you.

All values and results are and must be integers. You may use the expr command to do your calculations, or any other bash shell scripting method, such as ((expr)). Do not use any other languages other than bash shell scripting: this means that, among others, awk, sed, tcl, bc, perl, & the python languages and tools are off-limits for this assignment. Note that expr only works with whole numbers. When you calculate the average you must round to the nearest integer, where half values round away from 0 (i.e. 7.5 rounds up to 8, but -7.5 rounds down to -8). 

## p1gradingscript

The p1gradingscript file can be used to test the matrix script; place it in the same directory as the matrix script and run it like this: $ ./p1gradingscript matrix
