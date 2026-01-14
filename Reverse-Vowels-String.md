## Reverse Vowels of a String  
  
Method 1 :  
Two Pointers  
  
```cpp
class Solution 
{
public:
        char isVowel(char c)
        {
            c = tolower(c);
            return c=='a' || c=='e' || c=='i' || c=='o' || c=='u';
        }

    string reverseVowels(string s) 
    {
        int i=0;
        int j=s.size()-1;

        while(i<j)
        {
            if(!isVowel(s[i]))
                i++;

            else if(!isVowel(s[j]))
                j--;
                
            else
            {
                swap(s[i], s[j]);
                i++;
                j--;
            }
        }
            return s;
    }
};
```
  
Method 2 :  
Using Stacks  
  
```cpp
class Solution 
{
public:
    bool isVowel(char c) 
    {
        c = tolower(c);
        return c=='a' || c=='e' || c=='i' || c=='o' || c=='u';
    }

    string reverseVowels(string s) 
    {
        vector<char> vowels;

        for (char c : s)
            if (isVowel(c))
                vowels.push_back(c);

        int idx = vowels.size() - 1;
        for (char &c : s) 
        {
            if (isVowel(c))
                c = vowels[idx--];
        }
        return s;
    }
};
```
  
