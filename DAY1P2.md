# Maximum Subarray
---
- ## Question:
> Given an integer array nums, find the contiguous subarray (containing at least one number) which has the largest sum and return its sum.
> 
> A subarray is a contiguous part of an array.
---
- ## Example:
> Input: nums = [-2,1,-3,4,-1,2,1,-5,4]
> 
> Output: 6
> 
> Explanation: [4,-1,2,1] has the largest sum = 6.
---
- ## Solution:
**Code :**
```java
class Solution {
    public int maxSubArray(int[] nums) {
        int max=Integer.MIN_VALUE;
        int sum=0;
        for(int i=0;i<nums.length;i++)
        {
            sum=sum+nums[i];
            max=Math.max(sum,max);
            if(sum<0)
                sum=0;
        }
        return max;
    }
}
