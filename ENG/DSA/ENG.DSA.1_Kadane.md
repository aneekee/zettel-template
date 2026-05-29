---
tags:
  - idea

Created At: "2026-05-29 07:35"
---

The Kadane Algorithm is an algorithm for finding the max sum of the contiguous subarray.
It's more effective than the brute force approach -- O(n) vs O(n^2)
The key idea here is to

- iterate from left to right
- on each iteration either extend the current subarray OR start a new one
  - It makes sense to extend the current subarray if its sum is non-negative
  - It makes sense to start a new subarray if the current subarray sum is negative -- just skip the part that will always reduce the result sum

_When to use it?_
When you need to find a max sum of the contiguous subarray that contains negative numbers.

```js
// Kadane's Algorithm in JavaScript
function maxSubArraySum(arr) {
  // Initialize maxSum with the first element of the array
  let maxSum = arr[0];

  // currentSum will keep track of the current subarray sum
  let currentSum = arr[0];

  // Loop through the array starting from index 1
  for (let i = 1; i < arr.length; i++) {
    const num = arr[i];

    // Decide whether to start a new subarray at current element
    // or continue the current one
    currentSum = Math.max(num, currentSum + num);

    // Update maxSum if currentSum is greater
    maxSum = Math.max(maxSum, currentSum);
  }

  return maxSum;
}

// Example usage
const array = [-2, 1, -3, 4, -1, 2, 1, -5, 4];
console.log("Maximum subarray sum:", maxSubArraySum(array));
// Output: Maximum subarray sum: 6
```

## References

1. [[ENG.DSA.index]]
2. https://sassafras13.github.io/KadanesAlgo/
