## LVL 1 LEETCODE
## `Finished - 22`
</br>
</br>
</br>

## 700. Search in a Binary Search Tree

https://leetcode.com/problems/search-in-a-binary-search-tree/

> Given the root node of a binary search tree (BST) and a value. You need to find the node in the BST that the node's value equals the given value. Return the subtree rooted
> with that node. If such node doesn't exist, you should return NULL.

### Answer 
```
# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right
class Solution:
    def searchBST(self, root: TreeNode, val: int) -> TreeNode:
        if not root:
            return None
        if root.val == val:
            return root
        elif root.val > val:
            return self.searchBST(root.left, val)           
        else:
            return self.searchBST(root.right, val)	    
```

</br>
</br>
</br>

## 1480. Running Sum of 1d Array

https://leetcode.com/problems/running-sum-of-1d-array/

> Given an array nums. We define a running sum of an array as runningSum[i] = sum(nums[0]…nums[i]).
> Return the running sum of nums.

### Answer  

```
class Solution(object):
    def runningSum(self, nums):
	    result = []
	    result.append(nums[0])
	    for i in range(1, len(nums)):
		    result.append(result[-1]+nums[i])
	    return result
```
</br>
</br>
</br>
</br>

## 206. Reverse Linked List

https://leetcode.com/problems/reverse-linked-list/

> Reverse a singly linked list.

### Answer 
```
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next
class Solution:
    def reverseList(self, head: ListNode) -> ListNode:
    
        prev=None
        while head:
            temp = head
            head = head.next
            temp.next = prev
            prev = temp
        return prev
```

<br />
<br />
<br />

## 119. Pascal's Triangle II

https://leetcode.com/problems/pascals-triangle-ii/

> Given an integer rowIndex, return the rowIndexth row of the Pascal's triangle.

> Notice that the row index starts from 0.

### Answer 
```
class Solution:
    def getRow(self, rowIndex: int) -> List[int]:
        result = [1]*(rowIndex + 1)
        for i in range(1, rowIndex):
            for j in range(i, 0, -1):
                result[j] += result[j-1]
        return result
```

<br />
<br />
<br />

## 1431. Kids With the Greatest Number of Candies

https://leetcode.com/problems/kids-with-the-greatest-number-of-candies/

> Given the array candies and the integer extraCandies, where candies[i] represents the number of candies that the ith kid has.
> For each kid check if there is a way to distribute extraCandies among the kids such that he or she can have the greatest number of candies among them. Notice that multiple > > kids can have the greatest number of candies.

### Answer 

```
class Solution:
    def kidsWithCandies(self, candies: List[int], extraCandies: int) -> List[bool]:
        
        high_enough = max(candies) - extraCandies
        return [i >= high_enough for i in candies]
	
```
</br>
</br>
</br>
</br>


## 1108. Defanging an IP Address

https://leetcode.com/problems/defanging-an-ip-address/

> Given a valid (IPv4) IP address, return a defanged version of that IP address. A defanged IP address replaces every period "." with "[.]".

### Answer

```
class Solution:
    def defangIPaddr(self, address: str) -> str:
        return address.replace(".", "[.]")
```
</br>
</br>
</br>
</br>

## 1512. Number of Good Pairs

https://leetcode.com/problems/number-of-good-pairs/

> Given an array of integers nums.

> A pair (i,j) is called good if nums[i] == nums[j] and i < j.

> Return the number of good pairs.


### Answer 
```
class Solution(object):
    def numIdenticalPairs(self, nums):
    
        repeating = {}
        count = 0
        
        for i in nums:
            if i in repeating:
                
                if repeating[i] == 1:
                    count += 1
                else:
                    count += repeating[i]
                repeating[i] += 1
            else:
                repeating[i] = 1  
        return count
```
</br>
</br>
</br>
</br>

## 771. Jewels and Stones

https://leetcode.com/problems/jewels-and-stones/

> You're given strings J representing the types of stones that are jewels, and S representing the stones you have.  Each character in S is a type of stone you have.  You want 
> to know how many of the stones you have are also jewels.

> The letters in J are guaranteed distinct, and all characters in J and S are letters. Letters are case sensitive, so "a" is considered a different type of stone from "A".

### Answer 
```
class Solution:
    def numJewelsInStones(self, J: str, S: str) -> int:
        return sum(map(J.count, S))
```
</br>
</br>
</br>
</br>

## 1342. Number of Steps to Reduce a Number to Zero

https://leetcode.com/problems/number-of-steps-to-reduce-a-number-to-zero/

> Given a non-negative integer num, return the number of steps to reduce it to zero. If the current number is even, you have to divide it by 2, otherwise, you have to subtract > 1 from it.


### Answer 
#### JavaScript
```
const numberOfSteps = (num) => {
    let count = 0;
    while(num){
        if (num % 2) {
            count++;
            num--;
        } else {
            count++;
            num = num / 2;
        }
    }
    return count;
};
```

</br>
</br>
</br>
</br>

## 1528. Shuffle String

https://leetcode.com/problems/shuffle-string/

> Given a string s and an integer array indices of the same length.

> The string s will be shuffled such that the character at the ith position moves to indices[i] in the shuffled string.

> Return the shuffled string.

### Answer 
```
class Solution:
    def restoreString(self, s: str, indices: List[int]) -> str:
        
        result = []
        s_list = list(s)
        
        combined = zip(indices, s_list)
        x = list(combined)
        
        sorted_combined = sorted(x)
        
        for key, value in sorted_combined:
            result.append(value)
        winner = "".join(result)
        return winner
```

</br>
</br>
</br>
</br>

## 1528. Shuffle String

https://leetcode.com/problems/shuffle-string/

> Given a string s and an integer array indices of the same length.

> The string s will be shuffled such that the character at the ith position moves to indices[i] in the shuffled string.

> Return the shuffled string.

### Answer 
```
class Solution:
    def restoreString(self, s: str, indices: List[int]) -> str:
        
        result = []
        s_list = list(s)
        
        combined = zip(indices, s_list)
        x = list(combined)
        
        sorted_combined = sorted(x)
        
        for key, value in sorted_combined:
            result.append(value)
        winner = "".join(result)
        return winner
```

</br>
</br>
</br>
</br>

## 1365. How Many Numbers Are Smaller Than the Current Number

https://leetcode.com/problems/how-many-numbers-are-smaller-than-the-current-number/

> Given the array nums, for each nums[i] find out how many numbers in the array are smaller than it. That is, for each nums[i] you have to count the number of valid j's such
> that j != i and nums[j] < nums[i].

> Return the answer in an array.

### Answer 
```
class Solution:
    def smallerNumbersThanCurrent(self, nums: List[int]) -> List[int]:
        
        return([sorted(nums).index(i) for i in nums])
```

</br>
</br>
</br>
</br>

## 1281. Subtract the Product and Sum of Digits of an Integer

https://leetcode.com/problems/subtract-the-product-and-sum-of-digits-of-an-integer/

> Given an integer number n, return the difference between the product of its digits and the sum of its digits.

### Answer 
```
import math
class Solution:
    def subtractProductAndSum(self, n: int) -> int:
         # return (ixixi - x-i-i)
        
        arr = []
        
        for i in str(n):
            arr.append(int(i))
        
        product = math.prod(arr)
        summ = sum(arr)
        
        return (product - summ)
```

</br>
</br>
</br>
</br>

## 1313. Decompress Run-Length Encoded List

https://leetcode.com/problems/decompress-run-length-encoded-list/

> We are given a list nums of integers representing a list compressed with run-length encoding.

> Consider each adjacent pair of elements [freq, val] = [nums[2*i], nums[2*i+1]] (with i >= 0).  For each such pair, there are freq elements with value val concatenated in a
> sublist. Concatenate all the sublists from left to right to generate the decompressed list.

Return the decompressed list.

### Answer 
```
class Solution:
    def decompressRLElist(self, nums: List[int]) -> List[int]:
        
        decoded = []
        
        for i in range(0, len(nums), 2):
            freq = nums[i]
            value = nums[i+1]
            
            decoded.extend([value]*freq)
            
        return decoded
```
</br>
</br>
</br>
</br>

## 1389. Create Target Array in the Given Order

https://leetcode.com/problems/create-target-array-in-the-given-order/

> Given two arrays of integers nums and index. Your task is to create target array under the following rules:

> Initially target array is empty.
> From left to right read nums[i] and index[i], insert at index index[i] the value nums[i] in target array.
> Repeat the previous step until there are no elements to read in nums and index.
> Return the target array.

### Answer 
```
class Solution:
    def createTargetArray(self, nums: List[int], index: List[int]) -> List[int]:
        
        result = []
        x = list(zip(nums,index))
        
        for num,idx in x:
            result.insert(idx,num)
        return result
```
</br>
</br>
</br>
</br>

## 1290. Convert Binary Number in a Linked List to Integer

https://leetcode.com/problems/convert-binary-number-in-a-linked-list-to-integer/

> Given head which is a reference node to a singly-linked list. The value of each node in the linked list is either 0 or 1. 
> The linked list holds the binary representation of a number.

> Return the decimal value of the number in the linked list.

https://assets.leetcode.com/uploads/2019/12/05/graph-1.png

### Answer 
```
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next
class Solution:
    def getDecimalValue(self, head: ListNode) -> int:
        
        '''RECURSIVE'''
        
        res = []

        node = head
        while node:
            res.append(str(node.val))
            node = node.next
            
        combined = "".join(res)
        
        x = int(combined, 2)
        
        return x
```

</br>
</br>
</br>
</br>

## 191. Number of 1 Bits

https://leetcode.com/problems/number-of-1-bits/

> Write a function that takes an unsigned integer and returns the number of '1' bits it has (also known as the Hamming weight).

### Answer 
```
class Solution:
    def hammingWeight(self, n: int) -> int:
        return bin(n).count('1')
``` 

</br>
</br>
</br>
</br>


## 202. Happy Number

https://leetcode.com/problems/happy-number/

> Write an algorithm to determine if a number n is "happy".

> A happy number is a number defined by the following process: Starting with any positive integer, replace the number by the sum of the squares of its digits, and repeat the
> process until the number equals 1 (where it will stay), or it loops endlessly in a cycle which does not include 1. Those numbers for which this process ends in 1 are happy
> numbers.

> Return True if n is a happy number, and False if not.

### Answer 
```
class Solution:
    def isHappy(self, n: int) -> bool:
        
        seen = set()
        while n not in seen:
            seen.add(n)
            n = sum([int(x) **2 for x in str(n)])
        return n == 1
```

</br>
</br>
</br>
</br>


## 70. Climbing Stairs

https://leetcode.com/problems/climbing-stairs/

> You are climbing a stair case. It takes n steps to reach to the top.

> Each time you can either climb 1 or 2 steps. In how many distinct ways can you climb to the top?

### Answer 
```
class Solution:
    def climbStairs(self, n: int) -> int:
        """
        Input: 2
        Output: 2
        
        or
        
        Input: 10
        Output: 89
        """
        
        if n < 4:
            return n
        
        x1 = 2
        x2 = 3
        
        for i in range(n-3):
            x3 = x1 + x2
            x1 = x2
            x2 = x3
            
        return x3
```

</br>
</br>
</br>
</br>


## 1. Two Sum

https://leetcode.com/problems/two-sum/

> Given an array of integers nums and an integer target, return indices of the two numbers such that they add up to target.

> You may assume that each input would have exactly one solution, and you may not use the same element twice.

> You can return the answer in any order.

### Answer 
```
class Solution:
    def twoSum(self, nums: List[int], target: int) -> List[int]:
        # eneumerate to grab indices
        
        dict = {}
        
        for index, value in enumerate(nums):
            print(f"index = {index}, value = {value}")
            
            difference = target - value
            
            if difference in dict:              
                return[dict[difference], index] 
            
            else:
                dict[value] = index 
```

</br>
</br>
</br>
</br>


## 155. Min Stack

https://leetcode.com/problems/min-stack/

> Design a stack that supports push, pop, top, and retrieving the minimum element in constant time.

> push(x) -- Push element x onto stack.
> pop() -- Removes the element on top of the stack.
> top() -- Get the top element.
> getMin() -- Retrieve the minimum element in the stack.

### Answer 
```
class MinStack:
    def __init__(self):
        """
        initialize your data structure here.
        """
        self.stack = []
        

    def push(self, x):
        if not self.stack:self.stack.append((x,x)) 
        else:
            self.stack.append((x,min(x,self.stack[-1][1])))

    def pop(self):
        if self.stack: self.stack.pop()

    def top(self):
        if self.stack: return self.stack[-1][0]
        else: return None

    def getMin(self):
        if self.stack: return self.stack[-1][1]
        else: return None
        


# Your MinStack object will be instantiated and called as such:
# obj = MinStack()
# obj.push(x)
# obj.pop()
# param_3 = obj.top()
# param_4 = obj.getMin()
```

</br>
</br>
</br>
</br>

## 66. Plus One

https://leetcode.com/problems/plus-one/

> Given a non-empty array of digits representing a non-negative integer, increment one to the integer.

> The digits are stored such that the most significant digit is at the head of the list, and each element in the array contains a single digit.

### Answer 
```
class Solution:
    def plusOne(self, digits: List[int]) -> List[int]:
        
        strings = [str(digits) for digits in digits]
        a_string = "".join(strings)
        one_integer = int(a_string)

        x = one_integer + 1
        complete = map(int, str(x))
        
        return(complete)
```

FORMATING
[
##

url

>
>

### Answer 
```
```
]

