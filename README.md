# Efficient-String-Merging-Strategy

# Intuition

The goal is to merge two strings by alternating their characters, starting with the first string. If one string is longer than the other, the remaining characters from the longer string should be appended at the end. A natural way to approach this is to iterate over both strings in parallel and append characters from both strings to a result string. Once the shorter string runs out of characters, append the remaining characters from the longer string.

# Approach

1. We initialize an empty result string.
   
2. We determine the length of the shorter string using min(len(word1), len(word2)) to ensure we alternate up to the point where both strings still have characters left.
   
3. We loop through the indices of the shorter string and append alternating characters from both strings to the result.
   
4. Once the alternating characters are done, the remaining characters from the longer string are appended using slicing (word1[min_len:] and word2[min_len:]).
   
5. Finally, we return the result.

# Complexity

Time complexity: $$O(n)$$

The time complexity is linear because we iterate through each character of the strings once. We first iterate over the minimum length of both strings and then append the remaining characters from the longer string.


Space complexity: $$O(n)$$

The space complexity is also linear since the result string stores the final merged string, which is the sum of the lengths of word1 and word2.

# Code
```python []
class Solution(object):
    def mergeAlternately(self, word1, word2):
        result = ""
        min_len = min(len(word1), len(word2))
        for i in range(min_len):
            result += word1[i] + word2[i]
        # After the first loop
        result += word1[min_len:] + word2[min_len:]
        
        return result  # Add this line to return the result
```
