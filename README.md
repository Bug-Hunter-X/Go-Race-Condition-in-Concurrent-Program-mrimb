# Go Race Condition Example

This repository demonstrates a race condition in a Go program that uses goroutines and mutexes to protect a shared counter. Although it seems to be using mutex correctly, it might still produce an incorrect output in some cases.

## Problem

The program sums numbers from 0 to 999 concurrently using multiple goroutines.  A mutex is used to protect the `count` variable, but a subtle race condition can still occur.  This is because the loop increments `i` outside of the goroutine's scope and this variable can be modified before it's used inside the goroutine. Because of this, the program might not give the correct sum.