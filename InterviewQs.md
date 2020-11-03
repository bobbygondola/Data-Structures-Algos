# <div align="center">*Interview Questions*</div>

## Rotate String 

https://leetcode.com/interview/1/submissions/

> We are given two strings, A and B.

> A shift on A consists of taking string A and moving the leftmost character to the rightmost position.
> For example, if A = 'abcde', then it will be 'bcdea' after one shift on A. Return True if and only if A can become B after some number of shifts on A.

```
class Solution:
    def rotateString(self, A: str, B: str) -> bool:
        
        """
        Keep shifting until it matches, if it doesnt.. return False
        """
        
        # print("Left Rotation -> ", Lsecond + Lfirst)
        
        if A == B:
            return True
        
        if len(A) != len(B):
            return False
        
        for i in range(len(A)):
            if A[i:] + A[:i] == B:
                return True
        return False
```
<br />
<br />
<br />

## Majority Element

https://leetcode.com/interview/2/submissions/

> Given an integer array of size n, find all elements that appear more than ⌊ n/3 ⌋ times.

> Follow-up: Could you solve the problem in linear time and in O(1) space?

```
from collections import Counter

class Solution:
    def majorityElement(self, nums: List[int]) -> List[int]:
        '''
        return all i's if they appear more than n/3 times
        
        make a list
        
        add nums to counter
        
        check if the value of the key is greater than len(nums)/3
        
        add that key to the list
        '''
        
        res = []
        
        my_dict = Counter(nums)
        
        for key, val in my_dict.items():
            if val > int(len(nums)/3):
                res.append(key)
            
        return res
```
