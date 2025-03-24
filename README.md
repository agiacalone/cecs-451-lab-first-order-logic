
# CECS 451 Lab #2: First Order Logic and Logic Programming  

## Assignment Description

The purpose of this lab assignment is to give you some experience programming with logic programming and instituting constraints in a logic-based program. Your goal is to create a Sudoku solver program that brute-force solves any given 9x9 Sudoku puzzle. Your program should accept a matrix as an input (just like the previous lab assignment) and return a formatted output that resembles a Sudoku layout. Text output is fine, or you may output to a file (or both). Like the previous lab assignment, we will only be implementing the standard 9x9 Sudoku puzzle, so feel free to ignore any of the variants (meaning, don’t make this problem any harder than it has to be). Additionally, include a one-page paper discussing how you went about designing the sudoku solver, what specifics of the Prolog language make your life particularly easy (or diﬃcult!), any diﬃculties in designing/creating theprogram, and how eﬃciently or accurately the program runs along with any additional information that you think I might like to read. Also, please include a short comparison between this program and the previous hill-climbing lab assignment (these programs both essentially do the same thing–how do they diﬀer on a technical level?)

## Notes
We will be using [SWI-Prolog](http://www.swi-prolog.org) for this assignment. Since most of you have not coded in Prolog before, much of this assignment is learning the language sufficiently enough to solve the puzzles and discover the appropriate features of Prolog that can aid in solving them. [Docs for SWI-Prolog (and an intro tutorial) can be found on the language’s main page](http://www.swi-prolog.org/pldoc/doc_for?object=manual). Depending on how you design your solver, you might require extensive use of the "not" operator, `\+`. **Here’s what you need to know about this operator**:

- `\+` works as you would expect when all variables are completely instantiated (bound).

- Prolog tries to prove things, so if expression E contains unbound variables, `\+E` will try to find variable bindings that will make `E` true.

## Sample Code

Use the following three Sudoku puzzles as testers to evaluate the accuracy of your algorithm. Include, with your code submittal, screenshots of your program execution solving these puzzles.

#### Easy Difficulty:
```
[[8,_,_,9,_,3,_,_,1],
 [_,_,5,_,8,_,9,_,_],
 [_,3,_,_,_,_,_,6,_],
 [4,_,_,1,_,6,_,_,2],
 [_,6,_,_,_,_,_,4,_],
 [1,_,_,7,_,2,_,_,5],
 [_,7,_,_,_,_,_,9,_],
 [_,_,2,_,5,_,8,_,_],
 [9,_,_,4,_,1,_,_,3]]
```

#### Moderate Difficulty:

```
[[3,_,7,_,9,_,_,6,_],
 [9,5,_,_,_,8,_,_,2],
 [6,_,_,7,_,_,_,_,_],
 [_,3,_,_,6,_,_,5,_],
 [_,_,9,_,_,_,6,_,_],
 [_,8,_,_,4,_,_,2,_],
 [_,_,_,_,_,5,_,_,6],
 [4,_,_,9,_,_,_,1,3],
 [_,9,_,_,1,_,2,_,7]]
```
#### Fiendish Difficulty:
```
[[_,6,_,_,5,_,_,2,_],
[_,_,_,3,_,_,_,9,_],
[7,_,_,6,_,_,_,1,_],
[_,_,6,_,3,_,4,_,_],
[_,_,4,_,7,_,1,_,_],
[_,_,5,_,9,_,8,_,_],
[_,4,_,_,_,1,_,_,6],
[_,3,_,_,_,8,_,_,_],
[_,2,_,_,4,_,_,5,_]]
```

## Deliverables

Demonstrate your program for the instructor and submit a copy of your source code file(s), screenshots of a trial run with the sample test puzzles, and your one-page writeup on Beachboard Dropbox. Acceptable file submission formats for your writeup are: `.txt`, `.rtf`, `.doc`, `.docx`, or `.pdf`. Do not compress your files when submitting them. Please be sure to document and comment your assignment appropriately, or **it will not receive a grade**.