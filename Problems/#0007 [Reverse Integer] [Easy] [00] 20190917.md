# #0007 [Reverse Integer] [Easy]

Related Topics: `Math`

[See Problem](https://leetcode.com/problems/reverse-integer/)

## Submission Detail

Submitted: 2019/09/17

Detail URL: https://leetcode.com/submissions/detail/261626373/

Runtime: 56 ms

Runtime Rank: 10.91 %

Memory Usage: 14.2 MB

Memory Usage Rank:

## Problem Solving Mode of Mind

### English

### 繁體中文

## Submitted Code

Language: csharp

```csharp
public class Solution {
    public int Reverse(int x) {
        var source = x.ToString().Replace("-", "");
        var tempResult = "";
        for (var i = source.Length - 1; i >= 0; i--)
        {
            tempResult += source[i];
        }

        Console.WriteLine("tempResult: " + tempResult);
        //var result = Convert.ToInt32(tempResult);
        int.TryParse(tempResult, out int result);
        return (x < 0 ? -result : result);
    }
}
```

---

