# Remove Duplicates from Sorted Array

## Problem Statement
Given an integer array `nums` sorted in non-decreasing order, remove the duplicates **in-place** such that each unique element appears only once. The relative order of the elements should be kept the same. Then return the number of unique elements in `nums`.

### Requirements
- Modify the array `nums` such that the first `k` elements contain only the unique elements in the order they appeared initially.
- The remaining elements beyond `k` are not important.
- Return `k` as the count of unique elements.

## Example

### Example 1:
**Input:**
```java
nums = [1,1,2]
```
**Output:**
```java
2, nums = [1,2,_]
```
**Explanation:** The function returns `k = 2`, with the first two elements as `[1, 2]`. The remaining elements are irrelevant.

### Example 2:
**Input:**
```java
nums = [0,0,1,1,1,2,2,3,3,4]
```
**Output:**
```java
5, nums = [0,1,2,3,4,_,_,_,_,_]
```
**Explanation:** The function returns `k = 5`, with the first five elements as `[0,1,2,3,4]`.

## Solution
The following Java solution efficiently removes duplicates using a **two-pointer approach**:

### Approach
1. Use a pointer `j` to track the last unique element found.
2. Iterate through the array with `i`.
3. If `nums[j]` is different from `nums[i]`, increment `j` and update `nums[j]` with `nums[i]`.
4. Return `j + 1` as the count of unique elements.

### Code Implementation
```java
class Solution {
    public int removeDuplicates(int[] nums) {
        int j = 0;
        for(int i = 0; i < nums.length; i++) {
            if(nums[j] != nums[i]) {
                nums[++j] = nums[i];
            }
        }
        return j + 1;
    }
}
```

## Complexity Analysis
- **Time Complexity:** `O(n)` - Since we iterate through the array once.
- **Space Complexity:** `O(1)` - No additional space is used apart from modifying `nums` in-place.


