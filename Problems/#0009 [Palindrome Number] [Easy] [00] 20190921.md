# #0009 [Palindrome Number] [Easy]

Related Topics: `Math`

[See Problem](https://leetcode.com/problems/palindrome-number/)

## Submission Detail

Submitted: 2019/09/21

Detail URL: https://leetcode.com/submissions/detail/262639459/

Runtime: 60 ms

Runtime Rank: 90.12 %

Memory Usage: 15 MB

Memory Usage Rank: 20.00 %

## Problem Solving Mode of Mind

### English

### 繁體中文

## Submitted Code

Language: csharp

```csharp
public class Solution {
    public bool IsPalindrome(int x) {
        if (x < 0 || (x % 10 == 0 && x != 0))
        {
            return false;
        }
        else
        {
            int ox = x;
            int rev = 0;
            while (ox > rev)
            {
                int pop = ox % 10;
                ox /= 10;
                rev = rev * 10 + pop;
            }
            return (ox == rev || ox == rev / 10);
        }
    }
}
```

---

