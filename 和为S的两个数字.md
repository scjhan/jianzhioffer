> **Problem Description**  
输入一个递增排序的数组和一个数字S，在数组中查找两个数，是的他们的和正好是S，如果有多对数字的和等于S，输出两个数的乘积最小的。  

### 思路
由于是排好序的，而且是递增的，所以可以采用两边向中间靠拢查找的方法。
### 相距越远，积越小。
直接返回第一次找到的数即可。

****
### Code
```cpp
class Solution {
public:
    vector<int> FindNumbersWithSum(vector<int> array,int sum) {
		int l = 0, r = array.size() - 1, temp;
        
        while(l < r)
        {
            temp = array[l] + array[r];
            if (temp == sum)
            	return {array[l], array[r]};
            else if (temp > sum) --r;
            else ++l;
        }
        
        return {}; 
    }
};
```