# Lua pairs iterator and table modification

This repository demonstrates a potential issue with Lua's `pairs` iterator when used with tables modified during iteration. The bug.lua file contains code that uses `pairs` to traverse a nested table. Under certain conditions, this can lead to unexpected skips in the iteration or even an infinite loop.

The bugSolution.lua file provides a solution by using a different approach to iterate through the table. This solution demonstrates the use of a copy of the table to avoid issues during modification.

## How to reproduce
1. Clone the repository.
2. Run `lua bug.lua`
3. Observe the output (the issue may not be obvious at first run, but potential infinite loop or skipped element are signs).

## Solution
The solution is to use a copy of the table to iterate instead of modifying the original table during iteration.  This prevents issues with the iterator getting out of sync and missing entries.
