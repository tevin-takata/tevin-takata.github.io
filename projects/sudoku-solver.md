---
layout: project
type: project
image: img/sudokusquare.png
title: "Sudoku Solver"
date: 2022
published: true
labels:
  - Java
  - Recursion
summary: "Created a program that uses recursion to solve any solvable sudoku board."
---

In ICS211, we were given code that created a sudoku grid, and the assignment was to code a method that can solve a given sudoku board. This assignment was intended to help us understand recursion.

This is the 'fillSudoku' method that was used to start the recursion. It takes an input of a two-dimensional array (the sudoku board), and it creates a fixed BitSet that keeps track of the original board, then searches for the first empty square to start the recursion. It outputs 'true' or 'false' if the sudoku board has all 81 squares filled.

```
public static boolean fillSudoku (int [] [] sudoku) {
    
  BitSet fixedNumbers = new BitSet(81);
  
  for (int row = 0 ; row < 9 ; ++row) {
    for (int col = 0 ; col < 9 ; ++col) {
      if (sudoku[row][col] != 0) {
        fixedNumbers.set(row*9+col);
      }
    }
  }
    
  int start = 0;
  while(fixedNumbers.get(start)) {
    ++start;
  }   
  if(start == 81) {
    return true;
  }
  
  return fillSudokuAt(sudoku, start, fixedNumbers);
}
```

Below is the code 'fillSudokuAt' that is called by the 'fillSudoku' method that recurs until the board is solved, or is unsolvable. It takes an input of the two-dimensional sudoku array, the position it's at on the board, and the BitSet and outputs a boolean. It has a base case where all 81 squares are filled, and it checks if it is solved. Otherwise, it fills in the current square with every possible integer from 1-9 until it finds a valid attempt, and recursively tries every single square until it finds the first possible solution to the sudoku board. If no integers work for a given square, it returns false, and the sudoku board is unsolvable.
  
```
public static boolean fillSudokuAt(int[][] sudoku, int position, BitSet fixedNumbers) {
  if (position == 81) {
    return checkSudoku(sudoku, false);
  }
  
  int row = position/9;
  int col = position%9;
  
  ++position;
  while (fixedNumbers.get(position)) {
    ++position;
  }
  
  for (int guess = 1 ; guess < 10 ; ++guess) {
    sudoku[row][col] = guess;
    
    if (checkSudoku(sudoku, false)) {
      if (fillSudokuAt(sudoku, position, fixedNumbers)) {
        return true;
      }
    }
  }
  
  sudoku[row][col] = 0;
  return false;
}
```

This was a very intense first look into recursion, but it really helped my understanding of how recursion can be used in different contexts.
