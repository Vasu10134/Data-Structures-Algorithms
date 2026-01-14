## Valid Palindrome  

Method 1 :  
Two Pointer Approach

```cpp
class Solution {
public:
    bool isPalindrome(string s) 
    {    
        int i=0;
        int j=s.size()-1;

        while(i<j)
        {
            if(!isalnum(s[i]))
            i++;

            else if(!isalnum(s[j]))
            j--;

            else
            {
            if(tolower(s[i]) != tolower(s[j]))
            return false;

            i++;
            j--;
            }
        }
            return true;
    }
};
```

Method 2 :  
Reverse String, then Equating with Original
  
```cpp
class Solution 
{
public:
    bool isPalindrome(string s) 
    {
        string t;

        for (char c : s) 
        {
            if (isalnum(c))
                t.push_back(tolower(c));
        }

        int i = 0, j = t.size() - 1;
        while (i < j) 
        {
            if (t[i++] != t[j--])
                return false;
        }
        return true;
    }
};
```


