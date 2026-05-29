---
tags:
  - idea

Created At: "2026-05-29 07:42"
---

```js
var isPalindrome = function (s) {
  const cleaned = s.toLowerCase().replace(/[^a-z0-9]/g, "");

  let left = 0;
  let right = cleaned.length - 1;

  while (left < right) {
    if (cleaned[left] !== cleaned[right]) {
      return false;
    }

    left++;
    right--;
  }

  return true;
};
```

## References

1. [[ENG.DSA.TASKS.index]]
2. [[ENG.DSA.TASKS.COMPLEXITY.EASY]]
3. [[ENG.DSA.TASKS.TOPICS.1_Two_Pointers]]
4. https://leetcode.com/problems/valid-palindrome
