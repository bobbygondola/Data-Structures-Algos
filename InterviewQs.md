
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
