# EX 6D BRUTE FORCE ALGORITHM

## DATE :

## AIM :

To create a python program using brute force method of searching for the given substring in the main string.

## Algorithm :

1.Take two inputs: the main string and the substring to search for.

2.Create a regex pattern using the substring.

3.Search for the first match of the pattern in the main string.

4.If a match is found.Print the starting index of the match.

5.Continue searching for the next match, starting just after the current match.

6.Repeat step 4 until no more matches are found.

## Program:


### Developed by: VARSHINI S
### Register Number: 212222220056

```
import re
def match(string,sub):
    pattern = re.compile(str2)
    r = pattern.search(str1)
    while r:
        print("Found at index {}".format(r.start()))
        r = pattern.search(str1,r.start()+1)    

str1=input()
str2=input()
```

## Output :

![image](https://github.com/user-attachments/assets/75c27e26-c4dc-456e-971d-5c5ae641cb61)


## Result :

Thus the above program was executed successfully for searching the substring at respective index.
