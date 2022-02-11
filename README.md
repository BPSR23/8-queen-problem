# 8-queen-problem

You are given an 8x8 chessboard, find a way to place 8 queens such that no queen can attack any other queen on the chessboard. A queen can only be attacked if it lies on the same row, or same column, or the same diagonal of any other queen. Print all the possible configurations.
To solve this problem, we will make use of the Backtracking algorithm. The backtracking algorithm, in general checks all possible configurations and test whether the required result is obtained or not. For thr given problem, we will explore all possible positions the queens can be relatively placed at. The solution will be correct when the number of placed queens = 8.
The time complexity of this approach is O(N!).
Input Format - the number 8, which does not need to be read, but we will take an input number for the sake of generalization of the algorithm to an NxN chessboard.
Output Format - all matrices that constitute the possible solutions will contain the numbers 0(for empty cell) and 1(for a cell where queen is placed). Hence, the output is a set of binary matrices.
Visualisation from a 4x4 chessboard solution :
In this configuration, we place 2 queens in the first iteration and see that checking by placing further queens is not required as we will not get a solution in this path. Note that in this configuration, all places in the third rows can be attacked.
![image](https://user-images.githubusercontent.com/81702392/153544777-a4c7e45c-5ce7-489a-8156-3898aa0e1ec7.png)
As the above combination was not possible, we will go back and go for the next iteration. This means we will change the position of the second queen.
![image](https://user-images.githubusercontent.com/81702392/153544799-83314fdc-7c29-4d29-b4df-118ca617793e.png)
In this, we found a solution.
Now let's take a look at the backtracking algorithm and see how it works:
The idea is to place the queens one after the other in columns, and check if previously placed queens cannot attack the current queen we're about to place.
If we find such a row, we return true and put the row and column as part of the solution matrix. If such a column does not exist, we return false and backtrack*

Explanation of the above code solution:
![image](https://user-images.githubusercontent.com/81702392/153544809-8d2c5a45-a446-4e9c-bd3c-4463888035cc.png)

![image](https://user-images.githubusercontent.com/81702392/153544831-f543db8a-f1e2-4a90-9c20-d57ac306fb87.png)

Time Complexity Analysis
1.	the isPossible method takes O(n) time
2.	for each invocation of loop in nQueenHelper, it runs for O(n) time
3.	the isPossible condition is present in the loop and also calls nQueenHelper which is recursive
adding this up, the recurrence relation is:
T(n) = O(n^2) + n * T(n-1)
solving the above recurrence by iteration or recursion tree,
the time complexity of the nQueen problem is = O(N!)
