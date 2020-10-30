## <div align="center" > **LEVEL TWO LEETCODE**</div>
## <div align="center" >*`Finished - 3`* </div>

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

## 445. Add Two Numbers II

https://leetcode.com/problems/add-two-numbers-ii/

> You are given two non-empty linked lists representing two non-negative integers. 
> The most significant digit comes first and each of their nodes contain a single digit. 
> Add the two numbers and return it as a linked list.

### Answer 
```
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next
class Solution:
    def addTwoNumbers(self, l1: ListNode, l2: ListNode) -> ListNode:
        
        ans = []
        
        num_one = ""
        node = l1
        while node:
            num_one += str(node.val)
            node = node.next
        
        num_two = ""
        snode = l2
        while snode:
            num_two += str(snode.val)
            snode = snode.next
        
        x = int(num_one)
        y = int(num_two)
        
        
        res = (x+y)
        for i in str(res):
            ans.append(i)
        x = ",".join(ans)
        return(ListNode(x))
```

