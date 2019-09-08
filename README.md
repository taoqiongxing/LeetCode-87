# LeetCode-87扰乱字符串

### 题目链接：https://leetcode-cn.com/problems/scramble-string/

![image](https://github.com/taoqiongxing/LeetCode-87/blob/master/LeetCode-87)

# Code:
    class Solution:
        def isScramble(self, s1: str, s2: str) -> bool:
            if len(s1)==1:
                return s1==s2
            mid=len(s1)//2
            if len(set(s1[:mid])-set(s2[:mid]))==0:
                return self.isScramble(s1[:mid],s2[:mid]) and self.isScramble(s1[mid:],s2[mid:])
            elif len(set(s1[:mid])-set(s2[-mid:]))==0:
                return self.isScramble(s1[:mid],s2[-mid:]) and self.isScramble(s1[mid:],s2[:-mid])
            else:
                return False
