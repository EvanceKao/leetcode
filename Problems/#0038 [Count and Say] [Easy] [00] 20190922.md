# #0038 [Count and Say] [Easy]

Related Topics: `String`

[See Problem](https://leetcode.com/problems/count-and-say/)

## Submission Detail

Submitted: 2019/09/22

Detail URL: https://leetcode.com/submissions/detail/263140304/

Runtime: 80 ms

Runtime Rank: 96.99 %

Memory Usage: 28.4 MB

Memory Usage Rank:

## Problem Solving Mode of Mind

### English

### 繁體中文

## Submitted Code

Language: csharp

```csharp
public class Solution {
    static readonly Dictionary<int, string> dict = BuildMapping();

    public string CountAndSay(int n) {
        return dict[n];
    }

    static Dictionary<int, string> BuildMapping(int end = 30)
    {
        var mapping = new Dictionary<int, string>()
        {
            [1] = "1"
        };

        var previous = "1";
        for (var i = 2; i <= end; i++)
        {
            var result = "";
            var count = 1;
            var p = previous[0];
            for (var j = 1; j < previous.Length; j++)
            {
                if (p == previous[j])
                {
                    count++;
                }
                else
                {
                    result += $"{count.ToString()}{p}";
                    count = 1;
                }

                p = previous[j];
            }

            result += $"{count.ToString()}{previous[previous.Length - 1]}";
            Console.WriteLine($"i: {i}, r: {result}");
            mapping[i] = result;
            previous = result;
        }

        return mapping;
    }

}
```

---

