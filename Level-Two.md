## LEVEL TWO LEETCODE
## `Finished - 1`

<br />
<br />
<br />

## 24. Swap Nodes in Pairs

https://leetcode.com/problems/swap-nodes-in-pairs/
> Given a linked list, swap every two adjacent nodes and return its head.
>You may not modify the values in the list's nodes. Only nodes itself may be changed.

```
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next
class Solution:
    def swapPairs(self, head: ListNode) -> ListNode:
        if not head or not head.next:
            return head
        second = head.next
        head.next = self.swapPairs(second.next)
        second.next = head
        return second

```


