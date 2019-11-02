# #0053 [Maximum Subarray] [Easy]

Related Topics: `Array`, `Divide and Conquer`, `Dynamic Programming`

[See Problem](https://leetcode.com/problems/maximum-subarray/)

## Submission Detail

Submitted: 2019/09/22

Detail URL: https://leetcode.com/submissions/detail/263222142/

Runtime: Time Limit Exceeded

Runtime Rank:

Memory Usage:

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

        //Console.WriteLine($"l: {nums.Length}");
        var max = int.MinValue;
        var previous = 0;
        //var ps = 0;
        var dict = new Dictionary<int, int>();
        for (var i = 0; i < nums.Length; i++)
        {
            //dict[i] = (previous += nums[i]);
            //if (dict[i] > max)
            //    max = dict[i];

            var r = (previous + nums[i]);

            if (r < 0)
                dict[i] = r;

            //previous += nums[i];
            if (r > max)
            {
                //Console.WriteLine($"i: {i}, max: {max}, r: {r}");
                max = r;
            }

            //var ps = 0;
            for (var j = 0; j < i; j++)
            {
                //var r2 = r - ps - nums[j];
                //ps += nums[j];
                //Console.WriteLine($"j: {j}, r2: {r2}, ps: {ps}");

                if(!dict.ContainsKey(j))
                    continue;

                var r2 = r - dict[j];
                if (r2 > max)
                {
                    //Console.WriteLine($"i: {i}, j: {j}, max: {max}, r: {r}, r2: {r2}");
                    max = r2;
                }
            }

            previous = r;
        }

        return max;

        var previousSum = nums[0];
        for (var i = 1; i < nums.Length; i++)
        {
            for (var j = i; j < nums.Length; j++)
            {
                if (dict[j] - previousSum > max)
                    max = dict[j] - previousSum;
            }

            previousSum += nums[i];
        }

        return max;
    }
}
```

---

