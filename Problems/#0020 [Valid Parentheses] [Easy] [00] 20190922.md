# #0020 [Valid Parentheses] [Easy]

Related Topics: `String`, `Stack`

[See Problem](https://leetcode.com/problems/valid-parentheses/)

## Submission Detail

Submitted: 2019/09/22

Detail URL: https://leetcode.com/submissions/detail/262902309/

Runtime: 72 ms

Runtime Rank: 95.02 %

Memory Usage: 21 MB

Memory Usage Rank:

## Problem Solving Mode of Mind

### English

### 繁體中文

## Submitted Code

Language: csharp

```csharp
public class Solution {
    static Dictionary<char, char> Mapping = new Dictionary<char, char>()
    {
        ['('] = ')',
        ['['] = ']',
        ['{'] = '}',
    };

    public bool IsValid(string s) {
        if (s == "")
            return true;

        var list = new List<char>();
        foreach (var c in s)
        {
            if (Mapping.ContainsKey(c))
            {
                list.Add(c);
            }

            if (c == ')' || c == ']' || c == '}')
            {
                if (list.Count == 0 || c != Mapping[list[list.Count - 1]])
                    return false;

                list.RemoveAt(list.Count - 1);
            }
        }

        return list.Count == 0;
    }
}
```

---

