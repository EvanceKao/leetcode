# #0053 [Maximum Subarray] [Easy]

Related Topics: `Array`, `Divide and Conquer`, `Dynamic Programming`

[See Problem](https://leetcode.com/problems/maximum-subarray/)

## Submission Detail

Submitted: 2019/09/23

Detail URL: https://leetcode.com/submissions/detail/263353534/

Runtime: 96 ms

Runtime Rank: 91.21 %

Memory Usage: 24.3 MB

Memory Usage Rank:

## Problem Solving Mode of Mind

### English

### 繁體中文

## Submitted Code

Language: csharp

```csharp
public class Solution {
    public int MaxSubArray(int[] nums) {
        if (nums.Length == 1)
            return nums[0];

        var max = int.MinValue;
        var min = int.MaxValue;
        // previous sum of subarray
        var previous = 0;
        // sum of previous nums
        var pn = 0;

        for (var i = 0; i < nums.Length; i++)
        {
            var r = (previous + nums[i]);
            if (r > max)
            {
                max = r;
            }

            if (pn < min)
            {
                min = pn;
            }

            var r2 = r - min;
            if (r2 > max)
            {
                max = r2;
            }

            previous = r;
            pn += nums[i];
        }

        return max;

    }
}
```

---

