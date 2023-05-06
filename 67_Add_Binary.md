Given two binary strings a and b, return their sum as a binary string.

Example 1:

Input: a = "11", b = "1"

Output: "100"

Example 2:

Input: a = "1010", b = "1011"

Output: "10101"

Solution code:

    class Solution:
        def addBinary(self, a: str, b: str) -> str:
            res=""
            carry=0
            a,b=a[::-1],b[::-1]
            for i in range(max(len(a),len(b))):
                x=int(a[i]) if i<len(a) else 0
                y=int(b[i]) if i<len(b) else 0
                total=x+y+carry
                carry=total//2
                res=str(total%2)+res
            if carry==1:
                return "1"+res
            else:
                return res
