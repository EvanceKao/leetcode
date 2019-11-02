# #0007 [Reverse Integer] [Easy]

Related Topics: `Math`

[See Problem](https://leetcode.com/problems/reverse-integer/)

## Submission Detail

Submitted: 2019/09/21

Detail URL: https://leetcode.com/submissions/detail/262634907/

Runtime: 36 ms

Runtime Rank: 97.90 %

Memory Usage: 13.7 MB

Memory Usage Rank: 20.00 %

## Problem Solving Mode of Mind

### English

### 繁體中文

## Submitted Code

Language: csharp

```csharp
public class Solution {
    const int maxLimit = int.MaxValue / 10;
    const int minLimit = int.MinValue / 10;

    public int Reverse(int x) {
        int result = 0;


        try
        {
        while (x != 0)
        {
            int pop = x % 10;
            x /= 10;

            if (result > maxLimit || (result == maxLimit && pop > 7))
                return 0;

            if (result < minLimit || (result == minLimit && pop < -8))
                return 0;

            result = result * 10 + pop;
        }
        }
        catch
        {
            return 0;
        }
        return result;
    }
}
```

---

