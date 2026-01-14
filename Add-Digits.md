## Add Digits  
Given an integer num, repeatedly add all its digits until the result has only one digit, and return it.  
  
Method 1 :  
Digit Sum Iteration  
  
```cpp
class Solution
{
public:
    int addDigits(int num) 
    {
        while (num >= 10) 
        {
            int sum = 0;
            while (num > 0) 
            {
                {
                    sum += num % 10;
                    num /= 10;
                }
            }
            num = sum;
        }
        return num;
    }
};
```
  
