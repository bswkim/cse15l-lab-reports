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
This will search for all lines that do not contain the word "is" in all text files inside the pmed.0010069.txt file and print them.
```
grep -v "is" technical/plos/pmed.0010069.txt

output: 
kmsnoo@gimseon-us-MacBook-Air stringsearch-data % grep -v "is" technical/plos/pmed.0010069.txt


        current (288,000) and many previous Icelanders (more than 600,000 in total), but in
        deCODE Genetics, was set up to mine health-care data in Iceland, and to use it to assess
        a for-profit company. But the company has been supported by many Icelanders themselves,
        demonstrated by Icelanders donating blood samples with informed consent for research on
        PLoS Medicine that assesses how much genetic factors contribute to cancer
        The paper looked at 27 different types of cancers (all those with more than 200 cases)
        third- to fifth-degree) relatives. The seven cancers with the highest increased familial
        kidney, and bladder cancers. And, interestingly, three cancers—stomach, lung, and colon
        cancer—were also seen more frequently in mates of patients, indicating a shared
        cancers, for example, relatives of individuals with stomach, colon, rectal, or endometrial
        cancer were more likely to have any of these cancers.
        interviewing patients and family members. The size of the study (over 600,000 individuals,
        with 32,000 cancer cases) and the high quality of data enables the authors to detect subtle
        How robust are these data, and what do they mean for the biological understanding of
        already known to be associated with particular genetic defects, and syndromes that
        related cancers that include prostate, kidney, and bladder could possibly have a
        So, by highlighting these subtle links, the study's particular value may become
        apparent: deciding future avenues of investigation in the complex interrelationships that
        interact to produce cancer.
        
```
### Example 2: 
This command will search for all lines in the file The_Columbian.txt inside the government/Media dir that do not contain the word "But".
```
grep -v "But" technical/government/Media/The_Columbian.txt

output:
kmsnoo@gimseon-us-MacBook-Air stringsearch-data % grep -v "on" technical/government/Media/The_Columbian.txt 


The Columbian
Tuesday, June 11, 2002

Reaches U.S. High Court
PAUL QUEARY, Associated Press writer
legal services for the poor.
small or will be held for too short a time to earn interest for the
individual client.
The rule was later expanded to include real estate closing
offers.
which doles it out to 34 legal aid agencies around the state.
that defends private property rights sued in federal court in 1997
essentially steals the interest from the clients, an illegal taking
that's stolen from a lot of people."
Accounts exist in all 50 states so the case could have broad
impact.
Advocates argue that the program is an important source of legal
help for poor people forced to deal with civil legal matters
for help," said Barbara Clark, executive director of the Legal
very devastating."
Advocates also argue that interest is essentially created by the
if lawyers tried to set up a similar program to benefit the
clients.
But Samp argues that IOLTA programs essentially discourage
lawyers from setting up such pooled accounts that might benefit
their clients.
but a three-judge panel of the 9th U.S. Circuit Court of Appeals
overturned the ruling. Then the full 9th Circuit overruled its own
that the clients weren't harmed because the interest wouldn't be
earned otherwise.

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
This will search for the phrase "cancer treatment" in all text files inside the "biomed" folder, but instead of printing the matching lines, it will print only the names of the files that contain the word.
```
grep -l "cancer treatment" technical/biomed/*.txt

output: 
kmsnoo@gimseon-us-MacBook-Air stringsearch-data % grep -l "cancer treatment" technical/biomed/*.txt
technical/biomed/1471-2164-3-16.txt
technical/biomed/1471-2407-2-3.txt
technical/biomed/1471-2407-2-31.txt
technical/biomed/1471-2407-3-5.txt
technical/biomed/1471-2431-2-1.txt
technical/biomed/1472-6769-1-4.txt

```

### Example 2: 
This will search for the word "fatal" in all text files under the /stringsearch-data/technical/911report/ directory, and display only the names of the files that contain the word "fatal". 
```
grep -l "fatal" technical/911report/*.txt

output: 
kmsnoo@gimseon-us-MacBook-Air stringsearch-data % grep -l "fatal" technical/911report/*.txt
technical/911report/chapter-13.5.txt
technical/911report/chapter-3.txt
technical/911report/chapter-9.txt
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
This will search for lines that include the word article inside the text file of Gleiman's EMA Speech, but it will be searching it in case-insensitive manner. 
```
grep -ri "ArTicle" technical/government/Post_Rate_Comm/Gleiman_EMASpeech.txt

output:
kmsnoo@gimseon-us-MacBook-Air Post_Rate_Comm % grep -ri "ArTicle" technical/government/Post_Rate_Comm/Gleiman_EMASpeech.txt
Gleiman_EMASpeech.txt:Maynard expressed similar views in a news article this past summer.
Gleiman_EMASpeech.txt:July 20th Atlanta Journal-Constitution article, there goes much of
```

### Example 2: 
This command will search for the word "RNA" case-insensitively in 1471-2199-4-5.txt file and display the matching lines. Because it is case-insensitive right now, it searches for words like "Alternatively" and "RNase". 
```
grep -i "rna" technical/biomed/1471-2199-4-5.txt

output: 
kmsnoo@gimseon-us-MacBook-Air biomed % grep -i "rna" technical/biomed/1471-2199-4-5.txt 
        two parental DNA molecules [ 10 ] . Alternatively, RecF
        trapped in the agarose gel (see [ 24 25 ] ). An alternative
          mg/ml) and RNase A (20 mg/ml). The plugs were then washed
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
This will search for the word "Brian" in all text files inside the "911 report" folder and its subdirectories, and print the matching lines along with the names of the files that contain them.
```
grep -r "Brian" technical/911report

output: 
kmsnoo@gimseon-us-MacBook-Air stringsearch-data % grep -r "Brian" technical/911report
technical/911report/chapter-13.4.txt:                Sheridan's departure, see Austin Yamada interview (Dec. 23, 2003); Brian Sheridan
technical/911report/chapter-13.5.txt:                Brian C.,"dissemination of terrorism reporting," Dec. 29, 1999. See also NSA memo,
technical/911report/chapter-13.5.txt:                Brian Clark testimony, May 18, 2004 (videotaped); Civilian interview 3 (May 4,
technical/911report/chapter-13.5.txt:            85. For trouble descending, see Brian Clark testimony, May 18, 2004 (videotaped);
technical/911report/chapter-13.5.txt:            90. Brian Clark testimony, May 18, 2004 (videotaped); Civilian interview 1 (Mar. 2,
technical/911report/chapter-13.3.txt:            3. Trial testimony of Brian Parr, United States v. Yousef, No. S12 93 CR 180 (KTD)
technical/911report/chapter-13.3.txt:                William L. to Brian C., "dissemination of terrorism reporting," Dec. 29, 1999; NSA
technical/911report/chapter-13.3.txt:                Brian Sheridan interview (Feb. 25, 2004).
technical/911report/chapter-1.txt:    At 8:59, Flight 175 passenger Brian David Sweeney tried to call his wife, Julie. He left a message on their home answering machine that the plane had been hijacked. He then called his mother, Louise Sweeney, told her the flight had been hijacked, and added that the passengers were thinking about storming the cockpit to take control of the plane away from the hijackers.
technical/911report/chapter-6.txt:                recall any specific guidance on the topic from the secretary. Brian Sheridan-the
```

### Example 2: 
This command will search for the word "education program" in all files under the stringsearch-data/technical/biomed directory, including all subdirectories.
```
grep -r "education program" technical/biomed

output:
kmsnoo@gimseon-us-MacBook-Air stringsearch-data % grep -r "education program" technical/biomed
technical/biomed/1471-2458-3-20.txt:        education programs, opinions of hospital authorities, the
technical/biomed/1471-2407-3-18.txt:            approach to community-based education programs that
technical/biomed/1475-2875-2-10.txt:          low-cost outreach education programme, managed by a
technical/biomed/1472-6882-1-7.txt:        six-week exercise and education program produced a total
technical/biomed/1472-6963-3-11.txt:        formalizing a patient education program for these patients.
technical/biomed/1471-2296-3-3.txt:        several youth tobacco education programs have been created
technical/biomed/1471-2296-3-3.txt:        single session, in-class, youth tobacco education program.
technical/biomed/1471-2296-3-3.txt:        prevention/education programs and community/religious youth
```
---
> Souce: 
> [link](https://stackoverflow.com/questions/1987926/how-do-i-recursively-grep-all-directories-and-subdirectories). 
>  For sophistication, I used "man grep". 
---
