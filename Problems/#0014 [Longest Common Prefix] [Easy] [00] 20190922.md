# #0014 [Longest Common Prefix] [Easy]

Related Topics: `String`

[See Problem](https://leetcode.com/problems/longest-common-prefix/)

## Submission Detail

Submitted: 2019/09/22

Detail URL: https://leetcode.com/submissions/detail/262895500/

Runtime: 84 ms

Runtime Rank: 100 %

Memory Usage: 23.6 MB

Memory Usage Rank:

## Problem Solving Mode of Mind

### English

### 繁體中文

## Submitted Code

Language: csharp

```csharp
public class Solution {
    public string LongestCommonPrefix(string[] strs) {
        if (strs.Length == 0)
            return "";

        if (strs.Length == 1)
            return strs[0];

        string result = "";
        int i = 0;
        bool getShortestLength = false;

        while (!getShortestLength)
        {
            bool allSame = true;
            char previous = '1';
            foreach (var str in strs)
            {
                if (i > str.Length - 1)
                {
                    getShortestLength = true;
                    allSame = false;
                    break;
                }

                if (previous == '1')
                {
                    previous = str[i];
                    continue;
                }

                if (previous != str[i])
                {
                    getShortestLength = true;
                    allSame = false;
                    break;
                }
            }

            i++;

            if (allSame)
                result += previous;
        }

        return (result != "1" ? result : "");
    }
}
```

---

