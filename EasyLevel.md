"EASY" LEVEL LEETCODE QUESTIONS... Which means not easy
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



## 1108. Defanging an IP Address

https://leetcode.com/problems/defanging-an-ip-address/

> Given a valid (IPv4) IP address, return a defanged version of that IP address. A defanged IP address replaces every period "." with "[.]".

### Answer

```
class Solution:
    def defangIPaddr(self, address: str) -> str:
        return address.replace(".", "[.]")
```

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
[
##

url

>
>

### Answer 
```
```
]
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
