## Max Consecutive Ones  
  
Method 1 :  
Count 1's  
  
```cpp
class Solution
{
public:
    int findMaxConsecutiveOnes(vector<int>& nums)
{        
        int count = 0;
        int MaxCount = 0;

        map<int, int> mp;
        for(auto n : nums)
        {
            if(n == 1)
                count++;
            
            else
                count=0;

            MaxCount = max(MaxCount, count);
        }
        return MaxCount;
    }
};
```
