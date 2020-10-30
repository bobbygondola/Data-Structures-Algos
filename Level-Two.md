## <div align="center" > **LEVEL TWO LEETCODE**</div>
## <div align="center" >*`Finished - 2`* </div>

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

<br />
<br />
<br />

## 817. Linked List Components

https://leetcode.com/problems/linked-list-components/submissions/

> We are given head, the head node of a linked list containing unique integer values.

> We are also given the list G, a subset of the values in the linked list.

> Return the number of connected components in G, where two values are connected if they appear consecutively in the linked list.

### Answer 
```
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next
class Solution:
    def numComponents(self, head: ListNode, G: List[int]) -> int:
        
        gSet = set(G)
        current = head
        count = 0
        
        while current is not None:
            # Only counting the connected component as 1, because we count the 2nd or last piece of it [1,2,3] cause 3.next isnt in set
            # so we increment the whole [1,2,3] connected comp ONCE!
            if current.val in gSet and (current.next is None or current.next.val not in gSet):
                count += 1
                
            current = current.next
            
        return count
```

<br />
<br />
<br />


