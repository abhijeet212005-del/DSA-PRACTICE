<!-- problem:start -->

# [3Sum Closest](https://leetcode.com/problems/3sum-closest)

## Description

<!-- description:start -->

<p>You are given an integer array <code>nums</code> of length <code>n</code> and an integer <code>target</code>.</p>

<p>Find three integers at <strong>distinct indices</strong> in <code>nums</code> such that the sum is <strong>closest</strong> to <code>target</code>.</p>

<p>Return the sum of the three integers.</p>

<p>You may assume that each input would have <strong>exactly</strong> one solution.</p>

<p>&nbsp;</p>
<p><strong class="example">Example 1:</strong></p>

<pre>
<strong>Input:</strong> nums = [-1,2,1,-4], target = 1
<strong>Output:</strong> 2
<strong>Explanation:</strong> The sum that is closest to the target is 2. (-1 + 2 + 1 = 2).
</pre>

<p><strong class="example">Example 2:</strong></p>

<pre>
<strong>Input:</strong> nums = [0,0,0], target = 1
<strong>Output:</strong> 0
<strong>Explanation:</strong> The sum that is closest to the target is 0. (0 + 0 + 0 = 0).
</pre>

<p>&nbsp;</p>
<p><strong>Constraints:</strong></p>

<ul>
	<li><code>3 &lt;= nums.length &lt;= 500</code></li>
	<li><code>-1000 &lt;= nums[i] &lt;= 1000</code></li>
	<li><code>-10<sup>4</sup> &lt;= target &lt;= 10<sup>4</sup></code></li>
</ul>


<!-- description:end -->

## Solutions

<!-- solution:start -->

<!-- tabs:start -->

#### Java

```java
class Solution {
    public int threeSumClosest(int[] nums, int target) {
        Arrays.sort(nums);
       int n=nums.length;
       int c=nums[0]+nums[1]+nums[2];
       for(int i=0;i<n-2;i++){
        int l=i+1;
        int r=n-1;
        while(l<r){
            int s=nums[i]+nums[l]+nums[r];
            int diff=Math.abs(s-target);
            if(diff<Math.abs(c-target)){
                c=s;        
            }
            if(s==target)
            return target;
            else if(s<target){
                l++;
            }
            else
            r--;
        }
       }
       return c;
    }
}
```

<!-- tabs:end -->

<!-- solution:end -->

<!-- problem:end -->
