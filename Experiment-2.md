# Smallest Subarray with Sum Greater Than X

## Ques: Given a number x and an array of integers arr, find the smallest subarray with sum greater than the given value. If such a subarray do not exist return 0 in that case.
Examples:
Input: x = 51, arr[] = [1, 4, 45, 6, 0, 19]
Output: 3
Explanation: Minimum length subarray is [4, 45, 6]
Input: x = 100, arr[] = [1, 10, 5, 2, 7]
Output: 0
Explanation: No subarray exist
Link: https://www.geeksforgeeks.org/problems/smallest-subarray-with-sum-greater-than-x5651/1

## Aim
To find the smallest subarray whose sum is greater than a given value using sliding window technique.

---

## Problem Statement
Given a number `x` and an array `arr[]` of positive integers, find the smallest subarray with sum greater than `x`.  
If no such subarray exists, return `0`.

---

## Algorithm
1. Initialize variables: `start = 0`, `curr_sum = 0`, `min_len = n + 1`
2. Traverse array using `end`
3. Add elements to `curr_sum`
4. While `curr_sum > x`:
   - Update `min_len`
   - Remove starting element
   - Move `start`
5. If no valid subarray found, return `0`

---

## Python Code
```python
class Solution:
    def smallestSubWithSum(self, x, arr):
        n = len(arr)
        
        min_len = n + 1
        curr_sum = 0
        start = 0
        
        for end in range(n):
            curr_sum += arr[end]
            
            while curr_sum > x:
                min_len = min(min_len, end - start + 1)
                curr_sum -= arr[start]
                start += 1
        
        if min_len == n + 1:
            return 0
        
        return min_len
```

## Output

```bash
Compilation Completed

Input:
x = 51
arr[] = 1 4 45 6 0 19

Your Output:
3

Expected Output:
3
