# Chessboard-problem
Given a n by n board where n is of form 2k where k >= 1 (Basically n is a power of 2 with minimum value as 2). The board has one missing cell (of size 1 x 1). Fill the board using L shaped tiles. A L shaped tile is a 2 x 2 square with one cell of size 1×1 missing.
![image](https://github.com/palakpatel01/Chessboard-problem/assets/136109031/f7bd610a-c869-49d5-8cb6-7932179dcf1c)
Figure 1: An example input

This problem can be solved using Divide and Conquer. Below is the recursive algorithm.

// n is size of given square, p is location of missing cell
Tile(int n, Point p)

1) Base case: n = 2, A 2 x 2 square with one cell missing is nothing 
   but a tile and can be filled with a single tile.

2) Place a L shaped tile at the center such that it does not cover
   the n/2 * n/2 subsquare that has a missing square. Now all four 
   subsquares of size n/2 x n/2 have a missing cell (a cell that doesn't
   need to be filled).  See figure 2 below.

3) Solve the problem recursively for following four. Let p1, p2, p3 and
   p4 be positions of the 4 missing cells in 4 squares.
   a) Tile(n/2, p1)
   b) Tile(n/2, p2)
   c) Tile(n/2, p3)
   d) Tile(n/2, p3)

The below diagrams show working of above algorithm 
![image](https://github.com/palakpatel01/Chessboard-problem/assets/136109031/a3391a93-8e39-4878-95cb-064161204b2a)
Figure 2: After placing the first tile

![image](https://github.com/palakpatel01/Chessboard-problem/assets/136109031/22edcf7e-be07-4e29-8fcb-86ee8f4cf6d5)
Figure 3: Recurring for the first subsquare.

![image](https://github.com/palakpatel01/Chessboard-problem/assets/136109031/215ae99b-2440-4ec2-820a-38dca0bc8c85)
Figure 4: Shows the first step in all four subsquares.

Input :  size = 2 and mark coordinates = (0, 0)
Output : 
-1      1
1       1
Coordinate (0, 0) is marked. So, no tile is there. In the remaining three positions, 
a tile is placed with its number as 1.
Input : size = 4 and mark coordinates = (0, 0)
Output :
-1      3       2       2
3       3       1       2
4       1       1       5
4       4       5       5
















