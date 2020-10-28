format
##

url

>
>

### Answer 
```
```


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

