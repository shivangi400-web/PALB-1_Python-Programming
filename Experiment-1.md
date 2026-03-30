# Chocolate Distribution Problem

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

## Output

### Input
    3 4 1 9 56 7 9 12
    5

### Your Output
    6

### Expected Output
    6

### Result

| Status |
|--------|
| ✅ Correct Output |
