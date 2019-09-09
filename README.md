# LeetCode-87扰乱字符串

### 题目链接：https://leetcode-cn.com/problems/scramble-string/

![image](https://github.com/taoqiongxing/LeetCode-87/blob/master/LeetCode-87)

# Code:
    class Solution:
        def isScramble(self, s1: str, s2: str) -> bool:   
            def func(s1,s2):
                n=len(s1)
                if s1==s2:
                    return True 
                if n==1:
                    return False
                for i in range(1,n):
                    if func(s1[:i],s2[:i]) and func(s1[i:],s2[i:]):
                        return True
                    if func(s1[:i],s2[-i:]) and func(s1[i:],s2[:-i]):
                        return True
                return False
            return func(s1,s2)

### 时间超限，未解决emmmm！！！
