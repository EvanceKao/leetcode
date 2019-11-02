# #0026 [Remove Duplicates from Sorted Array] [Easy]

Related Topics: `Array`, `Two Pointers`

[See Problem](https://leetcode.com/problems/remove-duplicates-from-sorted-array/)

## Submission Detail

Submitted: 2019/09/22

Detail URL: https://leetcode.com/submissions/detail/263130962/

Runtime: 296 ms

Runtime Rank: 15.57 %

Memory Usage: 32.1 MB

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

        //var result = new List<int>();
        //result.Add(nums[0]);
        int ci = 0;
        int previous = nums[0];
        for (var i = 1; i < nums.Length; i++)
        {
            //Console.WriteLine($"{previous}, {nums[i]}");
            if (nums[i] != nums[ci])
            {
                ci++;
                Console.WriteLine($"ppp {nums[i]}");
                nums[ci] = nums[i];
                //ci++;
                //result.Add(nums[i]);
            }

            //previous = nums[i];
        }

        //nums = result.ToArray();
        foreach (var c in nums)
            Console.WriteLine($"c: {c}");
        return ci + 1;
    }
}
```

---

