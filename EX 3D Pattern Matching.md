# EX:3D - Pattern Matching
## DATE:

## AIM:

To write a python program to implement pattern matching on the given string using Brute Force algorithm.

## Algorithm

1. Initialize two pointers i (for s1, the text) and j (for s2, the pattern) to 0.
2. Loop through s1, compare s1[i] with s2[j]. If characters match, increment both i and j.
3. If characters do not match, shift the comparison window in s1 by one: i = i - j + 1, and reset j = 0.
4. If j reaches the length of s2, it means the full pattern has matched. Return the starting index: i - len(s2).
5. If the loop ends and j < len(s2), it means the pattern was not found in the text. Return 0.

   
## Program:
```
Program to implement the Pattern Matching

DEVELOPED BY    : NIRAUNJANA GAYATHRI G R
REGISTER NUMBER : 212222230096
```
```
def BF(s1,s2):
    i = 0
    j = 0
    while(i < len(s1) and j < len(s2)):
        if(s1[i] ==  s2[j]):
            i += 1
            j += 1
        else:
            i = i - j + 1
            j = 0
    if(j >= len(s2)):
        return i - len(s2)
    else:
        return 0
    #End here
if __name__ == "__main__":
    a1=input() 
    a2=input() 
    b=BF(a1,a2)
    print(b)
```

## Output:

![image](https://github.com/user-attachments/assets/4d883f30-c26d-470c-8868-77611d3aa320)


## Result:

The brute force substring search program executed successfully and returned the starting index of the match or 0 if no match was found.
