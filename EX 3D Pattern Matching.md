# EX 3D Pattern Matching
## DATE:16/5/25
## AIM:
Write a Python program for Bad Character Heuristic of Boyer Moore String Matching Algorithm





## Algorithm

1.Goal: Find where a pattern (pat) appears inside a text (txt).

2.Bad Character Heuristic: Prepares a table showing where each character last appeared in the pattern.

3.Start matching from the end of the pattern and move backwards.

4.If a mismatch happens, shift the pattern based on the bad character rule to skip unnecessary checks.

5.If a match is found, print the position and move the pattern ahead to look for more matches.


## Program:
```
Program to implement the Pattern Matching.
Developed by: GURUMOORTHI R
Register Number:  212222230042
```
```python
NO_OF_CHARS = 256
def badCharHeuristic(string, size):
    b = [-1]*NO_OF_CHARS
    for i in range(size):
        b[ord(string[i])]=i
    return b    
def search(txt, pat):
    m = len(pat)
    n = len(txt)
    badChar = badCharHeuristic(pat, m)
    s = 0
    while(s <= n-m):
        j = m-1
        while j>=0 and pat[j] == txt[s+j]:
            j -= 1
        if j<0:
            print("Pattern occur at shift = {}".format(s))
            s += (m-badChar[ord(txt[s+m])] if s+m<n else 1)
        else:
            s += max(1, j-badChar[ord(txt[s+j])])
def main():
    txt = input()                      #"ABAAABCD"
    pat = input()                      #"ABC"
    search(txt, pat)
 
if __name__ == '__main__':
    main()
```

## Output:

![image](https://github.com/user-attachments/assets/134fa85a-0e0c-42b4-8d99-c7d12395292a)


## Result:
Efficiently finds all positions where a pattern occurs in a text using the bad character heuristic
program executed successfully and returned the starting index of the match or 0 if no match was found.
