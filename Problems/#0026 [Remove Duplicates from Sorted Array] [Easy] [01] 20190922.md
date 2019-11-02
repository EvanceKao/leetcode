# #0026 [Remove Duplicates from Sorted Array] [Easy]

Related Topics: `Array`, `Two Pointers`

[See Problem](https://leetcode.com/problems/remove-duplicates-from-sorted-array/)

## Submission Detail

Submitted: 2019/09/22

Detail URL: https://leetcode.com/submissions/detail/263131204/

Runtime: 244 ms

Runtime Rank: 99.61 %

Memory Usage: 32.6 MB

Memory Usage Rank:

## Problem Solving Mode of Mind

### English

### 繁體中文

## Submitted Code

Language: csharp

```csharp
public class Solution {
    public int RemoveDuplicates(int[] nums) {
        if (nums.Length <= 1)
            return nums.Length;

        int ci = 0;
        for (var i = 1; i < nums.Length; i++)
        {
            //Console.WriteLine($"{previous}, {nums[i]}");
            if (nums[i] != nums[ci])
            {
                //ci++;
                nums[++ci] = nums[i];
                //ci++;
                //result.Add(nums[i]);
            }

            //previous = nums[i];
        }

        return ci + 1;
    }
}
```

---

