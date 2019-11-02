# #0058 [Length of Last Word] [Easy]

Related Topics: `String`

[See Problem](https://leetcode.com/problems/length-of-last-word/)

## Submission Detail

Submitted: 2019/09/23

Detail URL: https://leetcode.com/submissions/detail/263543250/

Runtime: 64 ms

Runtime Rank: 100.00 %

Memory Usage: 20.9 MB

Memory Usage Rank:

## Problem Solving Mode of Mind

### English

### 繁體中文

## Submitted Code

Language: csharp

```csharp
public class Solution {
    public int LengthOfLastWord(string s) {
        if (s == "")
            return 0;

        var r = 0;
        for (var i = s.Length - 1; i >= 0; i--)
        {
            if (s[i] != ' ')
            {
                r++;
            }
            else
            {
                if (r != 0)
                    break;
            }
        }

        return r;
    }
}
```

---

