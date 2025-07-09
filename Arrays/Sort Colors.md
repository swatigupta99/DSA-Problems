🧠 Problem: 75 Sort Colors Difficulty: Medium Link: [https://leetcode.com/problems/sort-colors/description/]

Given an array nums with n objects colored red, white, or blue, sort them in-place so that objects of the same color are adjacent, with the colors in the order red, white, and blue.

We will use the integers 0, 1, and 2 to represent the color red, white, and blue, respectively.

You must solve this problem without using the library's sort function.

 

Example 1:

Input: nums = [2,0,2,1,1,0]
Output: [0,0,1,1,2,2]
Example 2:

Input: nums = [2,0,1]
Output: [0,1,2]
 

Constraints:

n == nums.length
1 <= n <= 300
nums[i] is either 0, 1, or 2.

✅ Solution (Python):
1) class Solution:
    def sortColors(self, nums: List[int]) -> None:
        Zeros = 0
        Ones = 0
        Twos =0
        for i in range(0,len(nums)):
            if nums[i]==0:
                Zeros += 1
            if nums[i]==1:
                Ones +=1
            else:
                Twos +=1
        
        for i in range(0,Zeros):
            nums[i]=0
        for i in range(Zeros, Zeros+Ones):
            nums[i]=1
        for i in range(Zeros+Ones, len(nums)):
            nums[i]=2

2)In Single Traversal

class Solution:
    def sortColors(self, nums: List[int]) -> None:
        low = 0    
        mid = 0          
        high = len(nums) - 1 

        while mid <= high:
            if nums[mid] == 0:
                nums[low], nums[mid] = nums[mid], nums[low]
                low += 1
                mid += 1
            elif nums[mid] == 1:
                mid += 1
            else:  # nums[mid] == 2
                nums[mid], nums[high] = nums[high], nums[mid]
                high -= 1

🧠 Explanation: -
-low points to the next position to place 0
-mid traverses the list
-high points to the next position to place 2
-We swap and adjust pointers based on the value at mid

Time: O(n) – Single pass through the array.
