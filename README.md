# Leetcode-917.-Reverse-Only-Letters
# Description
Given a string s, reverse the string according to the following rules:

All the characters that are not English letters remain in the same position.
All the English letters (lowercase or uppercase) should be reversed.
Return s after reversing it.

# Solution
In the given problem we have been given a string in which we have to reverse all the alphabets(uppercase and lowercase) . If the character is not an alphabet then move forward to the next element .

Example:

Input: s = "a-bC-dEf-ghIj"

Output: "j-Ih-gfE-dCba"

"a-bC-dEf-ghIj"

 l           r ( reverse l and r since the character found is an alphabet and l+=1,r-=1.)
 

 "j-IC-dEf-ghba"
 
    l        r   (increment l by 1 becuase the next character is not an alphabet and reverse l and r since now both are alpabets.)

 "j-Ih-dEf-gCba" (the s[l] and s[r] are again alphabets hence swap the values and increment and decrement the l and r pointers)
 
     l      r 

"j-Ih-gEf-dCba" (again the next positions also contain alphabets hence swap)

      l   r

"j-Ih-dEf-gCba" 

       lr         (the decrementaed position in r is not an alphabet hence we ignored it and decremented it again)

Final : "j-Ih-dfE-gCba" 
        
