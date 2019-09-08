# LeetCode-87
扰乱字符串

题目链接：https://leetcode-cn.com/problems/scramble-string/

![image](https://github.com/taoqiongxing/relation-extraction-syntactic-indicator-lstm-cnn-/blob/master/Can%20Syntactic%20Indicators%20Help%20Relation%20Extraction/%E5%B9%BB%E7%81%AF%E7%89%871.png)

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
