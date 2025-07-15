🧠 Problem: 1 Two Sum: Easy Link: [https://leetcode.com/problems/two-sum/description/]

Given an array of integers nums and an integer target, return indices of the two numbers such that they add up to target.

You may assume that each input would have exactly one solution, and you may not use the same element twice.

You can return the answer in any order.

 

Example 1:

Input: nums = [2,7,11,15], target = 9
Output: [0,1]
Explanation: Because nums[0] + nums[1] == 9, we return [0, 1].
Example 2:

Input: nums = [3,2,4], target = 6
Output: [1,2]
Example 3:

Input: nums = [3,3], target = 6
Output: [0,1]
 

Constraints:

2 <= nums.length <= 104
-109 <= nums[i] <= 109
-109 <= target <= 109
Only one valid answer exists.

✅ Solution (Python):
class Solution:
    def twoSum(self, nums: List[int], target: int) -> List[int]:
        output = []
        dic1 = {}
        for i, num in enumerate(nums):
            diff = target-nums[i]
            if diff in dic1:
                output.append(i)
                output.append(dic1[diff])
                return output
            else:
                dic1[num]=i

🧠 Explanation: 

-Initialize Dictionary:seen = {} will store each number as key and its index as value.

-Iterate through the list: Using enumerate(nums), we get both index i and value num.

-Calculate Complement: For each number, calculate complement = target - num. This is the value we need to find in the previously seen numbers.

-Check if Complement Exists: If complement is already in seen, that means we have previously seen the number that can pair with num to reach target.

-Return Result: Return the index of the complement (seen[complement]) and the current index i.

-Store Current Number: If the complement is not found, store the current number and its index in seen for future reference.

Time: O(n)
