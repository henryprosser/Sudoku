# Solving Sudoku Puzzles Assignment

## Introduction

This project solves sudokus of varying difficulties. There are four difficulties of sudoku provided: very easy, easy, medium, and hard. In each category there are 15 sample sudokus.

## Constraint Satisfaction Problem

Sudoku is an example of a Constraint Satisfaction Problem (CSP). The problem is such that for each row, column and 3x3 box, the numbers 1-9 can only appear once. 

A CSP consists of three properties; Variables, Domain and Constraints. The core objective is to implement an algorithm that satisfies the constraints and finds a solution, which is a state that is both consistent and complete.

#### Definitions
- Variables = {A1, A2, ... , I8, I9} - 81 cells of 9x9 grid
- Domain = {1,2,3,4,5,6,7,8,9} - Values each variable can take
- Constraints = Numbers 1-9 can only appear once in each row, column or 3x3 box

## Algorithm
A combination of constraint propagation and depth first search is utilised. Constraint propagation is used initially to reduce the search space and then depth first search is implemented to find a solution (if it exists).

### Constraint propagation

Two forms of constraint propagation are employed. The first is if a cell has only one value, remove that value from the peers' (cells of the same row, column or box) domain of that given cell. The second is if a row, column or box has only one possible cell for a given value, insert the value into that cell.

### Depth first search

Picks an unsolved cell with the smallest number of possible values. These possible values are then iterated over and assigned to the cell one by one.
After the value has been assigned to the cell, a copy of the sudoku is made and search is then recursively called to find a solution. If after testing a given value, no solution is found then another value is tested. After all values of the given cell have been tested then another cell is chosen and tested. This cycle repeats until either the sudoku has been solved or no solution exists.   

## Method

1. A sudoku is taken as input and converted to a dictionary which matches each cell to a corresponding value. If the cell has already been filled in (a given value) then this value is assigned. If not, the cell is assigned all possible values 1-9. 

2. Constraint propagation is executed, cycling between the two forms. 

3. Once constraint propagation is no longer making any further progress (ie. no more cells are being solved) then depth first search is carried out.

4. If a solution is found, then the dictionary of cell values is converted back to a completed sudoku which is displayed.

5. If no solution is found, then a sudoku is returned where all values are assigned to be -1.




 

 


 

