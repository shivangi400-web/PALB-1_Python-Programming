# Chocolate Distribution Problem

## Ques: Given an array arr[] of positive integers, where each value represents the number of chocolates in a packet. Each packet can have a variable number of chocolates. There are m students, the task is to distribute chocolate packets among m students such that - i. Each student gets exactly one packet. ii. The difference between maximum number of chocolates given to a student and minimum number of chocolates given to a student is minimum and return that minimum possible difference.
Examples:
Input: arr = [3, 4, 1, 9, 56, 7, 9, 12], m = 5
Output: 6
Explanation: The minimum difference between maximum chocolates and minimum chocolates is 9 - 3 = 6 by choosing following m packets :[3, 4, 9, 7, 9].
Input: arr = [7, 3, 2, 4, 9, 12, 56], m = 3
Output: 2
Explanation: The minimum difference between maximum chocolates and minimum chocolates is 4 - 2 = 2 by choosing following m packets :[3, 2, 4].
Input: arr = [3, 4, 1, 9, 56], m = 5
Output: 55 Explanation: With 5 packets for 5 students, each student will receive one packet, so the difference is 56 - 1 = 55.
Link: https://www.geeksforgeeks.org/problems/chocolate-distribution-problem3825/1
## Aim
To distribute chocolate packets among students such that the difference between maximum and minimum chocolates is minimized.

---

## Problem Statement
Given an array `arr[]` of positive integers representing chocolates in packets and an integer `m` (number of students), distribute packets such that:
1. Each student gets exactly one packet
2. The difference between maximum and minimum chocolates is minimum

---

## Algorithm
1. Sort the array
2. Take a window of size `m`
3. Compute difference = `arr[i + m - 1] - arr[i]`
4. Find minimum among all such differences
5. Return the minimum difference

---

## Python Code
```python
class Solution:
    def findMinDiff(self, arr, M):
        
        if M > len(arr):
            return -1
        
        arr.sort()
        
        min_diff = float('inf')
        
        for i in range(len(arr) - M + 1):
            diff = arr[i + M - 1] - arr[i]
            min_diff = min(min_diff, diff)
        
        return min_diff

```
## Output

```bash
Input:
3 4 1 9 56 7 9 12
5

Output:
6
### Expected Output
    6

### Result

| Status |
|--------|
| ✅ Correct Output |
