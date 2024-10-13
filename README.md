# Quine-McCluskey-Method
Quine-McCluskey Algorithm
This project implements the Quine-McCluskey algorithm (also known as the tabulation method) for minimizing boolean expressions. The algorithm takes as input the minterms and optional don't-care terms and produces the minimized Boolean expression in terms of prime implicants (PIs). It handles various edge cases, including cyclic PIs and semi-cyclic PIs, and displays the result in a tabular form for clarity.

Features
Handles all edge cases:
Cyclic Prime Implicants: Detects and manages PIs that form cyclic dependencies.
Semi-Cyclic Prime Implicants: Detects and handles PIs with partial cyclic relationships.
Tabular PI representation: Presents the prime implicants (PIs) and essential prime implicants (EPIs) in a clear, tabular format.
Efficient minimization: Optimizes boolean expressions by reducing the number of literals.
User-friendly interface: Easy-to-read output for educational purposes.
Edge Case Handling
1. Cyclic PIs
In cases where a set of PIs forms a cycle (e.g., A implies B, B implies C, and C implies A), the algorithm can still find the essential PIs by breaking the cycle and resolving the expressions.

2. Semi-Cyclic PIs
For semi-cyclic dependencies (where only a subset of PIs is involved in a partial cycle), the algorithm properly identifies and isolates the non-cyclic part while simplifying the cyclic portion efficiently.

3. Degenerate and Redundant Terms
The algorithm efficiently skips over redundant prime implicants and simplifies boolean expressions by recognizing and handling degenerate cases where no further reduction is possible.

Table Representation of Prime Implicants (PIs)
Once the algorithm has generated all prime implicants, the final step is to display them in a tabular form, which makes it easy to identify the essential PIs (EPIs) and visualize the coverage of minterms.

Minterm	Prime Implicant 1	Prime Implicant 2	Prime Implicant 3	...
0	1	0	1	...
1	1	1	0	...
2	0	1	1	...
...	...	...	...	...
1 in a cell indicates that the prime implicant covers the respective minterm.
Essential Prime Implicants (EPIs) are highlighted or marked for clarity.
Input Format
The program takes the following input:

A list of minterms (required).
A list of don't-care terms (optional).
Example:
Enter number of variables: 4
Enter minterms space separated : 2 3 5 6 9 14
Enter dontcares: 0 1
Given minterms are 
['2', '3', '5', '6', '9', '14']
Don't care -
Don't Care:  ['0', '1']
================================================================================
   Group                                     Binary numbers
================================================================================
    0                                       : 0000, 
    1                                       : 0010, 0001, 
    2                                       : 0011, 0101, 0110, 1001, 
    3                                       : 1110, 
    4                                       : 
================================================================================
   Minterms                             Binary value
Usage Example
This section demonstrates how to run the program and what output to expect.

Input:
Enter the number of variables: 4
Enter the minterms (space-separated): 2 3 5 6 9 14
Enter the don't-care terms (space-separated): 0 1
bash
Copy code
Enter number of variables: 4
Enter minterms space separated: 2 3 5 6 9 14
Enter don'tcares: 0 1
Output:
text
Copy code
Given minterms are 
['2', '3', '5', '6', '9', '14']
Don't care -
Don't Care:  ['0', '1']

================================================================================
   Group                                     Binary numbers
================================================================================
    0                                       : 0000, 
    1                                       : 0010, 0001, 
    2                                       : 0011, 0101, 0110, 1001, 
    3                                       : 1110, 
    4                                       : 
================================================================================
   Minterms                             Binary value
===========================================================================================
   (2, 6)                                  0_10
   (1, 5)                                  0_01
   (1, 9)                                  _001
   (6, 14)                                 _110
   (0, 1, 2, 3)                            00__
===========================================
PI Chart Matrix:
===========================================
                : 2   3   5   6   9  14
(2, 6)          : X           X        
(1, 5)          :        X            
(1, 9)          :                X    
(6, 14)         :            X       X
(0, 1, 2, 3)    : X   X                
===========================================
All minterms are covered. Exiting.
===========================================
===========================================
Expression: 
BCD' + A'C'D + A'B' + B'C'D +
Explanation:
The input specifies 4 variables and provides the minterms and don't-care terms.
The minterms and don't-care terms are grouped by the number of ones in their binary representation.
The PI Chart Matrix shows how each prime implicant (grouped by tuples of minterms) covers specific minterms.
The minimized Boolean expression is generated as the final result.

A tabular representation of all PIs and their coverage.
Identification of Essential Prime Implicants (EPIs).
Running the Code
Clone the repository:

bash
Copy code
git clone https://github.com/solanki505/Quine-McCluskey-Method.git
Navigate to the project directory:

bash
Copy code
cd quine-mccluskey-algorithm
Run the program (assuming Python for this example):

bash
Copy code
python quine_mccluskey.py
Enter the minterms and don't-care terms when prompted, or use a pre-defined set of inputs.

Feel free to contribute to this project by opening issues or submitting pull requests. Make sure to follow the standard coding style and include tests for any new functionality.

