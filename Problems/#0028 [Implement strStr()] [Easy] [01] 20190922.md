# #0028 [Implement strStr()] [Easy]

Related Topics: `Two Pointers`, `String`

[See Problem](https://leetcode.com/problems/implement-strstr/)

## Submission Detail

Submitted: 2019/09/22

Detail URL: https://leetcode.com/submissions/detail/263139489/

Runtime: 68 ms

Runtime Rank: 99.35%

Memory Usage: 21.6 MB

Memory Usage Rank:

## Problem Solving Mode of Mind

### English

### 繁體中文

## Submitted Code

Language: csharp

```csharp
public class Solution {
    public int StrStr(string haystack, string needle) {
        //return haystack.IndexOf(needle);

        if (needle != "")
        {
            //if (haystack == "")
            //    return -1;

            var nl = needle.Length;
            for (var i = 0; i < haystack.Length; i++)
            {
                if (haystack[i] == needle[0])
                {
                    if (nl != 1)
                    {
                        if (i + nl > haystack.Length)
                            break;

                        bool find = true;
                        for (var j = 1; j < nl; j++)
                        {
                            if (haystack[i + j] != needle[j])
                            {
                                find = false;
                                break;
                            }
                        }

                        if (find)
                            return i;
                    }
                    else
                    {
                        return i;
                    }
                }
            }

            return -1;
        }

        return 0;


    }
}
```

---

