# 🔴 MY DSA PATTERN SHEET
 I AM MAKING THIS REVISION SERIES SO THAT IT SHOULD BE EASIER FOR ME TO REVISE ALL MY DSA PATTERNS:**

START WITH
**RECURSION:**
Apply recursion in those type of question where we have asked to find all (combination, permutation, etc...)
*THERE TOTAL THREE STAEPS IN RECURSION :*
1. *Base Case* -> THE MOST IMPORTANT THING IN RECURSION IS BASE CASE ALWAYS TAKE CARE OF BASE CASE**
2. *Do choice/work*
3. *Give back*
   ### 1. Letter Combinations of a Phone Number(**[LEETCODE](https://leetcode.com/problems/letter-combinations-of-a-phone-number/)**)

*,  IN this question ,*
**1> we have to store the value of each element in a map*
**2> and return res*


char ch = digits[idx]; // 2
string str = mp[ch]; // abc
for(int i = 0; i < str.length(); i++) { // iterative loop in abc
    temp.push_back(str[i]);             // push & First
    solve(idx + 1, temp, digits);       // move to idx+1 means 3 and proceed recursion on that
    temp.pop_back();                    // backtrack
}
2. COMBINATION:(LEETCODE)
​IN this question, WE will do the same this but as here give n and k where k is total number of combination and ranges from[1 to n]
​we will call the function from 1
​solve(1,k,temp,arr)--> while increing the idx +1 we will decrease the k: value(int, k-1, temp, arr)
​return result at the end

​3. Permutation:(LEETCODE)
​IN this question, WE will use map because we have elements like [1,2,3] and their permutation like [1,2,3] -> [1,3,2] -> [2,1,3] -> so we have to take care which is use previously like [1]-->idx
​2> if not then store in map and perform operations
for(int i = 0; i < n; i++) {
    if(st.find(nums[i]) == st.end()) {
        temp.push_back(nums[i]);
        st.insert(nums[i]);
        solve(temp, nums);
        st.erase(nums[i]);
        temp.pop_back();
    }
}
// at end save them in result and return
4>COMBINATION SUM(LEETCODE) -->
​Same as combination but elements can be reused. 
Decreased target but don't increase index immediately if element is picked
