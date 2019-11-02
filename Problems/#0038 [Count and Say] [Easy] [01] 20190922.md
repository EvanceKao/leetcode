# #0038 [Count and Say] [Easy]

Related Topics: `String`

[See Problem](https://leetcode.com/problems/count-and-say/)

## Submission Detail

Submitted: 2019/09/22

Detail URL: https://leetcode.com/submissions/detail/263198100/

Runtime: 84 ms

Runtime Rank: 91.34 %

Memory Usage: 22.4 MB

Memory Usage Rank: 37.50 %

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
            //var result = "";
            var result = new StringBuilder();
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
                    //result += $"{count.ToString()}{p}";
                    //result += $"{count}{p}";
                    result.Append($"{count.ToString()}{p}");
                    count = 1;
                }

                p = previous[j];
            }

            //result += $"{count.ToString()}{previous[previous.Length - 1]}";
            //Console.WriteLine($"i: {i}, r: {result}");
            //mapping[i] = result;
            //previous = result;

            result.Append($"{count.ToString()}{previous[previous.Length - 1]}");
            mapping[i] = result.ToString();
            previous = mapping[i];
        }

        return mapping;
    }

}
```

---

