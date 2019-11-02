# #0002 [Add Two Numbers] [Medium]

Related Topics: `Linked List`, `Math`

[See Problem](https://leetcode.com/problems/add-two-numbers/)

## Submission Detail

Submitted: 2019/09/21

Detail URL: https://leetcode.com/submissions/detail/262626153/

Runtime: 96 ms

Runtime Rank: 99.86 %

Memory Usage: 26.6 MB

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
    public ListNode AddTwoNumbers(ListNode l1, ListNode l2) {
        var result = new ListNode(0);
        ListNode l1t = l1, l2t = l2, lrt = result;
        int carry = 0;
        while (l1t != null || l2t != null)
        {
            int sum = carry + (l1t != null ? l1t.val : 0) + (l2t != null ? l2t.val : 0);
            l1t = l1t?.next;
            l2t = l2t?.next;

            carry = sum / 10;
            if (carry == 0)
            {
                lrt.next = new ListNode(sum);
            }
            else
            {
                lrt.next = new ListNode(sum - 10);
                lrt.next.next = new ListNode(1);
            }

            lrt = lrt.next;
        }

        return result.next;
    }
}
```

---

