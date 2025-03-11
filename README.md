# Leetcode-----1358
Number of Substrings Containing All Three Characters
//code in java 
class Solution {
    public int numberOfSubstrings(String s) {
        int[] count = {0, 0, 0}; // To count occurrences of 'a', 'b', 'c'
        int left = 0, result = 0;

        for (int right = 0; right < s.length(); right++) {
            count[s.charAt(right) - 'a']++;

            while (count[0] > 0 && count[1] > 0 && count[2] > 0) {
                result += s.length() - right; // Count valid substrings
                count[s.charAt(left) - 'a']--;
                left++; // Shrink window
            }
        }
        return result;
    }
}
