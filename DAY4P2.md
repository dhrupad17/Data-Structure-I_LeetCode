# Pascal's Triangle
---
- ## Question:
> Given an integer numRows, return the first numRows of Pascal's triangle.
> 
> In Pascal's triangle, each number is the sum of the two numbers directly above it as shown:
> 
![alt](https://upload.wikimedia.org/wikipedia/commons/0/0d/PascalTriangleAnimated2.gif)
---
- ## Example:
> Input: numRows = 5
> 
> Output: [[1],[1,1],[1,2,1],[1,3,3,1],[1,4,6,4,1]]
---
- ## Solution:
**Code :**
```java
class Solution {
    public List<List<Integer>> generate(int numRows) {
        List<List<Integer>> ans=new ArrayList<>();
        for(int i=0;i<numRows;i++)
        {
            ArrayList<Integer> temp=new ArrayList<>();
            for(int j=0;j<i+1;j++)
            {
                if(j==0||j==i)
                    temp.add(1);
                else
                {
                    int a=ans.get(i-1).get(j-1);
                    int b=ans.get(i-1).get(j);
                    temp.add(a+b);
                }
            }
            ans.add(temp);
        }
        return ans;
    }
}
