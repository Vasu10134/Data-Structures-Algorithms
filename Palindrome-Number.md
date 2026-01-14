## Palindrome Number  
  
Method 1 :  
Reverse Half  
  
```cpp
class Solution
{
public:
    bool isPalindrome(int x)
    {
        if (x < 0 || (x % 10 == 0 && x != 0))
            return false;

        int rev = 0;
        while (x > rev)
        {
            rev = rev * 10 + x % 10;
            x /= 10;
        }
        return x == rev || x == rev / 10;
    }
};
```
  
Method 2 :  
Reverse Full Number  
  
```cpp
class Solution
{
public:
    bool isPalindrome(int x)
    {
        if (x < 0) return false;

        int original = x;
        long long rev = 0;

        while (x > 0)
        {
            rev = rev * 10 + x % 10;
            x /= 10;
        }

        return rev == original;
    }
};
```
  
Method 3 :  
String + Two Pointers  
  
```cpp
class Solution
{
public:
    bool isPalindrome(int s)
{
        string x = to_string(s);
        int i = 0, j = x.size() - 1;

        while (i < j)
{
            if (x[i] != x[j])
                return false;
            i++;
            j--;
        }
        return true;
    }
};
```
  
