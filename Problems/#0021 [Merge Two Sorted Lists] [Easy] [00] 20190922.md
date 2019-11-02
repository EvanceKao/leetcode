# #0021 [Merge Two Sorted Lists] [Easy]

Related Topics: `Linked List`

[See Problem](https://leetcode.com/problems/merge-two-sorted-lists/)

## Submission Detail

Submitted: 2019/09/22

Detail URL: https://leetcode.com/submissions/detail/263123404/

Runtime: 96 ms

Runtime Rank: 81.46 %

Memory Usage: 25.1 MB

Memory Usage Rank:

## Problem Solving Mode of Mind

### English

### 繁體中文

## Submitted Code

Language: csharp

```csharp
/**
 * Definition for singly-linked list.
 * public class ListNode {
 *     public int val;
 *     public ListNode next;
 *     public ListNode(int x) { val = x; }
 * }
 */
public class Solution {
    public ListNode MergeTwoLists(ListNode l1, ListNode l2) {
        if (l1 == null)
            return l2;

        if (l2 == null)
            return l1;

        ListNode l1tp = null, l1t = l1, l2t = l2;
        while (l2t != null)
        {
            Console.WriteLine("l2t: " + l2t.val.ToString());

            while (l1t != null)
            {
                if (l2t.val <= l1t.val)
                {
                    //

                    if (l1tp != null)
                    {
                        // l2t.next = l1t;
                        l1tp.next = new ListNode(l2t.val)
                        {
                            next = l1t
                        };
                    }
                    else
                    {
                        l1 = new ListNode(l2t.val)
                        {
                            next = l1
                        };
                    }
                    break;
                }

                if (l1t.next == null)
                {
                    l1t.next = new ListNode(l2t.val);
                    break;
                }

                l1tp = l1t;
                l1t = l1t.next;
            }

            l1tp = null;
            l1t = l1;
            l2t = l2t.next;
        }

        return l1;
    }
}
```

---

