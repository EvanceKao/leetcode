# #0002 [Add Two Numbers] [Medium]

Related Topics: `Linked List`, `Math`

[See Problem](https://leetcode.com/problems/add-two-numbers/)

## Submission Detail

Submitted: 2019/09/17

Detail URL: https://leetcode.com/submissions/detail/261618438/

Runtime: 152 ms

Runtime Rank: less than 3.17 %

Memory Usage: 26.7 MB

Memory Usage Rank: less than 2.27 %

## Problem Solving Mode of Mind

### English

### 繁體中文

## Submitted Code

Language: csharp

```csharp
// Definition for singly-linked list.
//public class ListNode {
//    public int val;
//    public ListNode next;
//    public ListNode(int x) { val = x; }
//}

public class Solution {
    public ListNode AddTwoNumbers(ListNode l1, ListNode l2) {
        var l1Num = RecoverNumber(l1);
        var l2Num = RecoverNumber(l2);
        var resultString = (l1Num + l2Num).ToString();

        Console.WriteLine("resultString: " + resultString);

        ListNode ln = new ListNode(Convert.ToInt32(resultString[resultString.Length - 1].ToString()));
        //ListNode ln = null;
        ListNode tempListNode = ln;

        if (resultString.Length > 1)
        {
            for (var i = resultString.Length - 2; i >= 0; i--)
            {
                var currcntListNode = new ListNode(Convert.ToInt32(resultString[i].ToString()));
                tempListNode.next = currcntListNode;
                tempListNode = tempListNode.next;
            }
        }

        Console.WriteLine("valid: " + RecoverNumber(ln).ToString());
        return ln;

        //ListNode ln = new ListNode(Convert.ToInt32(resultString[0].ToString()));
        //ListNode tempListNode = ln;
        //
        //if (resultString.Length > 1)
        //{
        //    for (var i = 1; i < resultString.Length; i++)
        //    {
        //        var currcntListNode = new ListNode(Convert.ToInt32(resultString[i].ToString()));
        //        tempListNode.next = currcntListNode;
        //        tempListNode = tempListNode.next;
        //    }
        //}
        //
        //Console.WriteLine("valid: " + RecoverNumber(ln).ToString());
        //return ln;

        //ListNode lastListNode = null;
        //for (var i = resultString.Length - 1; i >= 0; i--)
        //{
        //    var currcntListNode = new ListNode(Convert.ToInt32(resultString[i].ToString()));
        //    if (lastListNode != null)
        //    {
        //        //lastListNode.next = currcntListNode;
        //        currcntListNode.next = lastListNode;
        //    }
        //    lastListNode = currcntListNode;
        //}
        //
        //Console.WriteLine("valid: " + RecoverNumber(lastListNode).ToString());
        //return lastListNode;

        //ListNode ln = null;
        //foreach (var c in resultString)
        //{
        //    //ListNode newListNode = null;
        //    BuildListNodes()
        //}
    }

    private BigInteger RecoverNumber(ListNode ln)
    {
        string tempString = "";
        tempString += ln.val.ToString();

        while (ln.next != null)
        {
            ln = ln.next;
            tempString += ln.val.ToString();
        }

        Console.WriteLine("RecoverNumber: " + tempString);

        var resultString = ReverseString(tempString);
        //return Convert.ToDecimal(resultString);
        return BigInteger.Parse(resultString);
    }

    private string ReverseString(string source)
    {
        string result = "";
        for (var i = source.Length - 1; i >= 0; i--)
        {
            result += source[i].ToString();
        }

        Console.WriteLine("ReverseString: " + result);

        return result;
    }

    private void BuildListNodes(ref ListNode originListNode, int nextVal)
    {
        if (originListNode == null)
        {
            originListNode = new ListNode(nextVal);
        }
        else
        {
            originListNode.next = new ListNode(nextVal);
        }
    }
}
```

---

