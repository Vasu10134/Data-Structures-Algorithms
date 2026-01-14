## Majority Element  
  
Method 1 :  
Using Boyer's Moore Algorithm  
  
```cpp
class Solution 
{
public:
    int majorityElement(vector<int>& nums) 
    {
        int count = 0;
        int candidate = 0;
        
        for (int num : nums) 
        {
            if (count == 0) 
                candidate = num;
            
            if (num == candidate) 
                count++;

            else 
                count--;
        }      
        return candidate;
    }
};
```
  
Method 2 :  
Sorting the nums array then returning middle element  

```cpp
class Solution  
{  
public:  
    int majorityElement(vector<int>& nums)   
    {  
        sort(nums.begin(), nums.end());  
        return (nums[nums.size()/2]);  
    }  
};
```
  
Method 3 :  
Comparing nums[i] with nums[j], increment count  
  
```cpp  
class Solution  
{  
public:  
    int majorityElement(vector<int>& nums)  
    {  
        int x = nums.size();  
  
        for (int i = 0; i < x; i++)  
        {  
            int count = 1;  
            for (int j = i + 1; j < x; j++)
                {  
                if (nums[i] == nums[j])  
                {  
                    count++;  
                }  
            }  
            if (count > x / 2)  
            {  
                return nums[i];  
            }  
        }  
        return -1;  
    }  
};  
```
  
Method 4 :  
Using Maps (Unordered Maps)  
  
```cpp
class Solution
{
public:
    int majorityElement(vector<int>& nums)
{
        unordered_map<int, int> mp;
        int n = nums.size();

        for (int num : nums)
{
            mp[num]++;
            if (mp[num] > n / 2)
                return num;
        }
        return -1;
    }
};
```
  

