# Reshape the Matrix
---
- ## Question:
> In MATLAB, there is a handy function called reshape which can reshape an m x n matrix into a new one with a different size r x c keeping its original data.
> 
> You are given an m x n matrix mat and two integers r and c representing the number of rows and the number of columns of the wanted reshaped matrix.
> 
> The reshaped matrix should be filled with all the elements of the original matrix in the same row-traversing order as they were.
> 
> If the reshape operation with given parameters is possible and legal, output the new reshaped matrix; Otherwise, output the original matrix.
---
- ## Example:
![alt](https://assets.leetcode.com/uploads/2021/04/24/reshape1-grid.jpg)
> Input: mat = [[1,2],[3,4]], r = 1, c = 4
> 
> Output: [[1,2,3,4]]
---
- ## Solution:
**Code :**
```java
class Solution {
    public int[][] matrixReshape(int[][] mat, int r, int c) {
        int row=mat.length;
        int col=mat[0].length;
        if(row*col!=r*c)
            return mat;
        int[][] result=new int[r][c];
        int rrow=0;
        int rcol=0;
        for(int i=0;i<row;i++)
        {
            for(int j=0;j<col;j++)
            {
                result[rrow][rcol]=mat[i][j];
                rcol++;
                if(rcol==c)
                {
                    rcol=0;
                    rrow++;
                }
            }
        }
        return result;
    }
}
