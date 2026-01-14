## Single Number  
  
Method 1 :  
Using XOR Solution  
  
```cpp
class Solution
{
public:
    int singleNumber(vector<int>& nums) 
    {
        int ans=0;
        for(int i : nums)
        {
            ans ^= i;
        }
        return ans;
    }
};
```
  
Method 2 :  
Using Maps  
  
```cpp
class Solution
{
public:
    int singleNumber(vector<int>& nums)
{
        unordered_map<int, int> mp;
        for (int x : nums)
            mp[x]++;
        for (auto &p : mp)
            if (p.second == 1)
                return p.first;
        return -1;
    }
};
```
  
