# #0013 [Roman to Integer] [Easy]

Related Topics: `Math`, `String`

[See Problem](https://leetcode.com/problems/roman-to-integer/)

## Submission Detail

Submitted: 2019/09/21

Detail URL: https://leetcode.com/submissions/detail/262885592/

Runtime: 76 ms

Runtime Rank: 99.63 %

Memory Usage: 24.6 MB

Memory Usage Rank: 20.00 %

## Problem Solving Mode of Mind

### English

### 繁體中文

## Submitted Code

Language: csharp

```csharp
public class Solution {
    private static readonly Dictionary<char, int> romanNumeralsMapping = new Dictionary<char, int>()
    {
        ['I'] = 1,
        ['V'] = 5,
        ['X'] = 10,
        ['L'] = 50,
        ['C'] = 100,
        ['D'] = 500,
        ['M'] = 1000,
    };

    public int RomanToInt(string s) {
        //if (s.Length == 1)
        //    return romanNumeralsMapping[s[0]];

        int result = 0;
        int n1 = romanNumeralsMapping[s[0]];
        for (var i = 1; i < s.Length; i++)
        {
            //int n1 = romanNumeralsMapping[s[i - 1]];
            int n2 = romanNumeralsMapping[s[i]];

            if (n1 >= n2)
            {
                result += n1;

                //if (i + 1 < s.Length)
                //    i++;
            }
            else
            {
                result -= n1;
            }

            n1 = n2;
        }

        result += romanNumeralsMapping[s[s.Length - 1]];
        return result;
    }
}
```

---

