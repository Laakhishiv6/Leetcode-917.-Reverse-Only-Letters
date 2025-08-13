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
 
    l        r  (increment l by 1 becuase the next character is not an alphabet and reverse l and r since now both are alpabets.)

 "j-Ih-dEf-gCba" (the s[l] and s[r] are again alphabets hence swap the values and increment and decrement the l and r pointers)
 
     l      r 

"j-Ih-gEf-dCba" (again the next positions also contain alphabets hence swap)

      l   r

"j-Ih-dEf-gCba" 

       lr         (the decrementaed position in r is not an alphabet hence we ignored it and decremented it again)

Final : "j-Ih-dfE-gCba" 
        
# Algorithm
1. Convert the string s into a list of characters so it can be modified in place.
2. Initialize two pointers: l = 0 (start of the list) and r = len(s) - 1 (end of the list)
3. Loop while l < r:
4. If s[l] is not an alphabet letter (not s[l].isalpha()), move l right (l += 1).
5. Else if s[r] is not an alphabet letter, move r left (r -= 1).
6. Else (both are letters), swap s[l] and s[r], then move both pointers inward (l += 1, r -= 1).
7. End loop when l >= r.
8. Join the list back into a string and return it.
# Code
class Solution:

    def reverseOnlyLetters(self, s: str) -> str:
        s=list(s)
        l,r=0,len(s)-1
        while l<r:
            if not s[l].isalpha():
                l+=1
            elif not s[r].isalpha():
                r-=1
            else:
                s[l],s[r]=s[r],s[l]
                l+=1
                r-=1
        return ''.join(s)
# Complexity
Time Complexity:

The loop runs while l < r, and in each step at least one pointer (l or r) moves inward.

Each character in the string is checked at most once from the left and once from the right.

Checking isalpha() is O(1).

Swapping and pointer movement are also O(1) operations.

Overall Time Complexity: O(n), where n is the length of the string.

Space Complexity:

We convert the string into a list of characters → requires O(n) space.

No other data structures are used apart from a few variables.

Overall Space Complexity: O(n)
