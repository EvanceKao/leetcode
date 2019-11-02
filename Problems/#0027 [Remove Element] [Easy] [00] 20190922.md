# #0027 [Remove Element] [Easy]

Related Topics: `Array`, `Two Pointers`

[See Problem](https://leetcode.com/problems/remove-element/)

## Submission Detail

Submitted: 2019/09/22

Detail URL: https://leetcode.com/submissions/detail/263135556/

Runtime: 232 ms

Runtime Rank: 99.70 %

Memory Usage: 29.2 MB

Memory Usage Rank:

## Problem Solving Mode of Mind

### English

### 繁體中文

## Submitted Code

Language: csharp

```csharp
public class Solution {
    public int RemoveElement(int[] nums, int val) {
        if (nums.Length == 0)
            return 0;

        int ci = 0;
        for (var i = 0; i < nums.Length; i++)
        {
            if (val != nums[i])
            {
                nums[ci++] = nums[i];
            }
        }

        return ci;
    }
}
```

---

