# Intersection of Two Arrays II
---
- ## Question:
> Given two integer arrays nums1 and nums2, return an array of their intersection. Each element in the result must appear as many times as it shows in both arrays and you may return the result in any order.
---
- ## Example:
> Input: nums1 = [1,2,2,1], nums2 = [2,2]
> 
> Output: [2,2]
---
- ## Solution:
**Code :**
```java
class Solution {
    public int[] intersect(int[] nums1, int[] nums2) {
        int l1=nums1.length;
        int l2=nums2.length;
        if(l1==0)
            return nums1;
        if(l2==0)
            return nums2;
        Arrays.sort(nums1);
        Arrays.sort(nums2);
        int i=0,j=0,k=0;
        while(i<l1 && j<l2)
        {
            if(nums1[i]<nums2[j])
                i++;
            else if(nums2[j]<nums1[i])
                j++;
            else if(nums1[i]==nums2[j])
            {
                nums1[k++]=nums1[i];
                i++;
                j++;
            }
        }
        return Arrays.copyOfRange(nums1,0,k);
    }
}
