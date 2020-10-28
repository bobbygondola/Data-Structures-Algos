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



## Defanging an IP Address

https://leetcode.com/problems/defanging-an-ip-address/

> Given a valid (IPv4) IP address, return a defanged version of that IP address. A defanged IP address replaces every period "." with "[.]".

### Answer

```
class Solution:
    def defangIPaddr(self, address: str) -> str:
        return address.replace(".", "[.]")
```

