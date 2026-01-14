## Find The Difference  
  
Method 1 :  
Using XOR  
  
```cpp
class Solution
{
public:
    char findTheDifference(string s, string t)
    {
        char ans = 0;
        for (char c : s) ans ^= c;
        for (char c : t) ans ^= c;
        return ans;
    }
};
```
  
Method 2 :  
ASCII Sum Solution  
  
```cpp
class Solution
{
public:
    char findTheDifference(string s, string t)
    {
        int sum_s = 0;
        for (char c : s) sum_s += c;

        int sum_t = 0;
        for (char c : t) sum_t += c;

        return (char)(sum_t - sum_s);
    }
};
```  
  
