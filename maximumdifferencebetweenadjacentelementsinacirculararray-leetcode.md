# Maximum Difference Between Adjacent Elements in a Circular Array - LeetCode
  
  ## Problem Description
  
  Can you solve this real interview question? Maximum Difference Between Adjacent Elements in a Circular Array - Given a circular array nums, find the maximum absolute difference between adjacent elements.

Note: In a circular array, the first and last elements are adjacent.
  
  ### Examples:
  ```
  Example 1:

Input: nums = [1,2,4]

Output: 3

Explanation:

Because nums is circular, nums[0] and nums[2] are adjacent. They have the maximum absolute difference of |4 - 1| = 3.

Example 2:

Input: nums = [-5,-10,-5]

Output: 5

Explanation:

The adjacent elements nums[0] and nums[1] have the maximum absolute difference of |-5 - (-10)| = 5.
  ```
  
  ### Constraints:
  
  Constraints:

 * 2 <= nums.length <= 100
 * -100 <= nums[i] <= 100
  
  
  ### Approach:
  ---
  
  #### approach 1:
  

  #### Solution Language:
  ```  C++  ```
  ```
  class Solution {
public:
    int maxAdjacentDistance(vector<int>& nums) {
        int max_num=INT_MIN;
        int n= nums.size();
       

        for(int i=0; i<nums.size(); i++){
            int idx = (i+1) % n; 
            int ans = abs(nums[i]-nums[idx]);
            max_num=max(ans,max_num);
        }

        return max_num;
    }
};
  ```
  