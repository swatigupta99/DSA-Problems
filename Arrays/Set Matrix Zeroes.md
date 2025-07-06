## 🧠 Problem: Binary Search (LeetCode #704)
**Difficulty:** Easy  
**Link:** [https://leetcode.com/problems/set-matrix-zeroes/description/]


### ❓ Problem Statement:
Given an m x n integer matrix matrix, if an element is 0, set its entire row and column to 0's.

You must do it in place.

 

Example 1:


Input: matrix = [[1,1,1],[1,0,1],[1,1,1]]
Output: [[1,0,1],[0,0,0],[1,0,1]]
Example 2:


Input: matrix = [[0,1,2,0],[3,4,5,2],[1,3,1,5]]
Output: [[0,0,0,0],[0,4,5,0],[0,3,1,0]]
 

Constraints:

m == matrix.length
n == matrix[0].length
1 <= m, n <= 200
-231 <= matrix[i][j] <= 231 - 1

### ✅ Solution (Python):
```python
class Solution:
    def setZeroes(self, matrix: List[List[int]]) -> None:
        m = len(matrix)
        n = len(matrix[0])
        row_no = []
        column_no = []
        for i in range(0,m):
            for j in range (0,n):
                if matrix[i][j]==0:
                    row_no.append(i)
                    column_no.append(j)
                else:
                    continue
        for i in row_no:
            for j in range(0,n):
                matrix[i][j]=0
        
        for i in column_no:
            for j in range(0,m):
                matrix[j][i]=0

```

---

### 🧠 Explanation:

-Determine the number of rows m and columns n in the matrix.
-Traverse the entire matrix.
-If an element is 0, store its row index in row_no and column index in column_no.
-For each row index stored in row_no, set all elements in that row to 0.
-For each column index stored in column_no, set all elements in that column to 0.

---

### ⏱️ Time Complexity:

-Time Complexity: O(m × n)

-Space Complexity: O(m + n) – due to extra space used for tracking rows and columns.
