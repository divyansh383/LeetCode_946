# LeetCode 946. Validate Stack Sequences

## Problem
Given two integer arrays pushed and popped each with distinct values, return true if this could have been the result of a sequence of push and pop operations on an initially empty stack, or false otherwise.


```java
class Solution {
    public boolean validateStackSequences(int[] pushed, int[] popped) {
        Stack<Integer> st=new Stack<>();
        int i=0;
        int j=0;
        for(i=0;i<pushed.length;i++){
            st.push(pushed[i]);
            while(!st.isEmpty() && j<popped.length && popped[j]==st.peek()){
                st.pop();
                j++;
            }
        }
        while(j<popped.length && !st.isEmpty() && popped[j]==st.peek()){
            st.pop();
            j++;
        }
        
        if(i==pushed.length && j==popped.length && st.isEmpty()){
            return true;
        }return false;
    }
}
```

## Link

[LeetCode](https://leetcode.com/ndivyansh29/)
