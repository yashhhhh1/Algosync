# Maximum Difference Between Even and Odd Frequency I - LeetCode
  
  ## Problem Description
  
  Can you solve this real interview question? Maximum Difference Between Even and Odd Frequency I - You are given a string s consisting of lowercase English letters.

Your task is to find the maximum difference diff = freq(a1) - freq(a2) between the frequency of characters a1 and a2 in the string such that:

 * a1 has an odd frequency in the string.
 * a2 has an even frequency in the string.

Return this maximum difference.
  
  ### Examples:
  ```
  Example 1:

Input: s = "aaaaabbc"

Output: 3

Explanation:

 * The character 'a' has an odd frequency of 5, and 'b' has an even frequency of 2.
 * The maximum difference is 5 - 2 = 3.

Example 2:

Input: s = "abcabcab"

Output: 1

Explanation:

 * The character 'a' has an odd frequency of 3, and 'c' has an even frequency of 2.
 * The maximum difference is 3 - 2 = 1.
  ```
  
  ### Constraints:
  
  Constraints:

 * 3 <= s.length <= 100
 * s consists only of lowercase English letters.
 * s contains at least one character with an odd frequency and one with an even frequency.
  
  
  ### Approach:
  ---
  
  #### approach 1:
  

  #### Solution Language:
  ```  C++  ```
  ```
  class Solution {
public:
    int maxDifference(string s) {

        unordered_map<char,int>mp;

        for(auto x:s){
            mp[x]++;
        }

        int max_odd=INT_MIN;
        int max_even=INT_MIN;
        int min_even=INT_MAX;

        for(auto x:mp){
            if(x.second %2 == 0 ){
                max_even=max(x.second,max_even);
                min_even=min(x.second,min_even);
            }else{
                max_odd=max(x.second,max_odd);
            }
        }
        
        // if(max_odd>max_even){
        //     return (max_odd-max_even);
        // }else{
        //     return (max_odd-min_even);
        // }

        return (max_odd-min_even);
        
    }
};
  ```
  