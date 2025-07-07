🧠 Problem: Move Zeros (Problem #283)
Difficulty: Medium Link: [https://leetcode.com/problems/move-zeroes/description/]

❓ Problem Statement:
Given an integer array nums, move all 0's to the end of it while maintaining the relative order of the non-zero elements.

Note that you must do this in-place without making a copy of the array.

 

Example 1:

Input: nums = [0,1,0,3,12]
Output: [1,3,12,0,0]
Example 2:

Input: nums = [0]
Output: [0]
 

Constraints:

1 <= nums.length <= 104
-231 <= nums[i] <= 231 - 1

✅ Solution (Python):

class Solution:
    
    def moveZeroes(self, nums: List[int]) -> None:
        if len(nums)==1:
            return
        else:
            n = len(nums)
            i = 0
            for j in range(n):
                if nums[j] != 0:
                    nums[i], nums[j] = nums[j], nums[i]
                    i += 1
🧠 Explanation:
-i always points to the position where the next non-zero element should go.
-If nums[j] is not zero, we swap it with nums[i].
-If nums[i] == nums[j], the swap does nothing, but i is still moved forward.

⏱️ Time Complexity:
-Time Complexity: O(n)
