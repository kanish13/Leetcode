The valid parentheses problem involves checking that:

All the parentheses are matched, i.e., every opening parenthesis has a corresponding closing parenthesis.

The matched parentheses are in the correct order, i.e., an opening parenthesis should come before the closing parenthesis.

![Screenshot 2023-04-30 231018](https://user-images.githubusercontent.com/111358462/235367929-8348a8f9-bac2-4e00-9fd7-489835f288e7.png)

Solution Code: 

    class Solution:
        def isValid(self, s: str) -> bool:
            if len(s)==1 or len(s)==3 or s[0]==")" or s[0]=="}" or s[0]=="]":
              return False
            di={"(":")","[":"]","{":"}"}
            a=[]
            c=[]
            for i in s:
              if i=="(" or i=="[" or i=="{":
                a.append(i)
              else:
                if len(a)!=0:
                    b=a.pop()
                    if di[b]==i:
                      c.append(b)
                      c.append(i)
                      pass
                    else:
                      return False
            if len(s)==len(c):
              return True

