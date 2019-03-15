# LeetCode 1 Two Sum

## 问题重述

给定整数数组`num`和整数`target`，在数组中寻找两个数，使其和为`target`，并输出其下标，输入保证结果唯一。

## 解法

### 解法一：暴力搜索

双层循环枚举所有组合。时间复杂度O(n^2).

```
class Solution:
    def twoSum(self, nums: List[int], target: int) -> List[int]:
        for i in range(0,len(nums)):
            for j in range(i+1,len(nums)):
                if nums[i]+nums[j]==target:
                    return [i,j]
```

### 解法二：字典

维护一个储存(k,v)=(值，下标）的字典。每读入一个值，在字典中寻找key=target-该值的记录。若有，则直接输出结果，否则增加一条记录。时间复杂度O(n).

```
class Solution:
    def twoSum(self, nums: List[int], target: int) -> List[int]:
        dic={}
        for i in range(0,len(nums)):
            if target-nums[i] in dic:
                return [dic[target-nums[i]],i]
            else:
                dic[nums[i]]=i
```

