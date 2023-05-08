# Lab Report 3 

## GREP COMMAND OPTIONS

## 1. -v 
```
--invert-match
grep -v "pattern" [file]
```

### This option inverts the matching. That is, it selects all lines that do not match the given pattern.
---
### Example 1: 
This will search for all lines that do not contain the word "research" in all text files inside the "plos" folder and print them.
```
grep -v "research" stringsearch-data/technical/plos/*
```
### Example 2: 
This command will search for all lines in all files under the stringsearch-data/technical/government/ directory that do not contain the word "secret".
```
grep -v "secret" stringsearch-data/technical/government/*
```
---
> Souce: 
> [stackoverflow link](https://stackoverflow.com/questions/29710366/linux-grep-command). 
>  For sophistication, I used "man grep". 
---

## 2. -l
```
--files-with-matches
grep -l "pattern" [file]
```

### This option prints only the names of the files that contain at least one match, instead of printing the matching lines.
---
### Example 1:
This will search for the phrase "treatment" in all text files inside the "biomed" folder, but instead of printing the matching lines, it will print only the names of the files that contain the word.
```
grep -l "cancer treatment" stringsearch-data/technical/biomed/*.txt
```

### Example 2: 
This will search for the word "fire" in all text files under the /stringsearch-data/technical/911report/ directory, and display only the names of the files that contain the word "fire". 
```
grep -l "fire" ~/stringsearch-data/technical/911report/*.txt
```

---
> Souce: 
> I used ChatGPT question "give me some options for grep command".
>  For sophistication, I used "man grep". 
---

## 3. -i
```
--ignore-case
grep -i "pAtTeRn" [file]
```

### This option makes the search case-insensitive, i.e., it matches both uppercase and lowercase versions of the given pattern. 
---
### Example 1: 
This will search for lines that include the word vaccine inside the government dir, but it will be searching it in case-insensitive manner. 
```
grep -ri "vaccine" stringsearch-data/technical/government/*.txt
```

### Example 2: 
This command will search for the word "cancer" case-insensitively in all .txt files under the ~/stringsearch-data/technical/biomed/ directory and display the matching lines.
```
grep -i "cancer" stringsearch-data/technical/biomed/*.txt
```

---
> Souce: 
> I used ChatGPT question "give me some options for grep command".
>  For sophistication, I used "man grep". 
---

## 4. -r 
```
--recursive
grep -r "pattern" /path/directory
```

### This option enables a recursive search through all subdirectories, searching for files that match the given pattern.
---
### Example 1: 
This will search for the word "terrorism" in all text files inside the "911 report" folder and its subdirectories, and print the matching lines along with the names of the files that contain them.
```
grep -r "terrorism" stringsearch-data/technical/911report
```

### Example 2: 
This command will search for the word "pattern" in all files under the stringsearch-data/technical/ directory, including all subdirectories.
```
grep -r "pattern" ~/stringsearch-data/technical/
```
---
> Souce: 
> [link](https://stackoverflow.com/questions/1987926/how-do-i-recursively-grep-all-directories-and-subdirectories). 
>  For sophistication, I used "man grep". 
---
