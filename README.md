# LEETCODE-Arrays-1295
## Problem Statement

Given an array of integers, return how many of them contain an even number of digits.

### Example

```java
Input: [12, 345, 2, 6, 7896]  
Output: 2  
Explanation:  
12 and 7896 have an even number of digits.
```

## How It Works

The `Solution` class contains two methods:

### 1. `count(int n)`
- Converts an integer `n` to a string.
- Returns the number of digits by using `length()` of the string.

### 2. `findNumbers(int[] nums)`
- Iterates through the array `nums`.
- Calls `count()` on each element to find the number of digits.
- Increments a counter if the number of digits is even.
- Returns the final count.

## Code

```java
class Solution {
    public static int count(int n) {
        String a = Long.toString(n);
        return a.length();
    }

    public int findNumbers(int[] nums) {
        int count = 0;
        for (int i = 0; i < nums.length; i++) {
            int x = count(nums[i]);
            if (x % 2 == 0) count++;
        }
        return count;
    }
}
```
## Note

- This solution uses `Long.toString(n)` to safely handle large integers (although the array is of `int`, not `long`).
- Can be optimized by using `Math.log10(n) + 1` instead of string conversion.
