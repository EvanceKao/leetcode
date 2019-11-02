# #0035 [Search Insert Position] [Easy]

Related Topics: `Array`, `Binary Search`

[See Problem](https://leetcode.com/problems/search-insert-position/)

## Submission Detail

Submitted: 2019/09/22

Detail URL: https://leetcode.com/submissions/detail/263140304/

Runtime: 88 ms

Runtime Rank: 98.66 %

Memory Usage: 23.9 MB

Memory Usage Rank:

## Problem Solving Mode of Mind

### English

### 繁體中文

## Submitted Code

Language: csharp

```csharp
public class Solution {
    public int SearchInsert(int[] nums, int target) {
        if (nums.Length == 0)
            return 0;

        var ci = 0;
        for (var i = 0; i < nums.Length; i++)
        {
            if (target > nums[i])
                ci++;
        }
        return ci;
    }
}
```

---

