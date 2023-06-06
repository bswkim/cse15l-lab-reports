<img src="helpbar.png"/>
<img src="writebar.png"/>
**What environment are you using (computer, operating system, web browser, terminal/editor, and so on)?**

- VSCode, Google Chrome, MacOS operating system

**Detail the symptom you're seeing. Be specific; include both what you're seeing and what you expected to see instead. Screenshots are great, copy-pasted terminal output is also great. Avoid saying “it doesn't work”.**

I'm encountering an error while running a script, and I could use some help. The error message states that the package org.junit does not exist. Here are the details of my setup:
<img src="error5.png"/>
I have a script that clones a student's submission, compiles the code, and runs JUnit tests. The script uses ```JUnit version 4.13.2```, and I have the necessary JUnit library files (```junit-4.13.2.jar and hamcrest-core-1.3.jar```) in the lib directory relative to the script.
I keep getting the ```package org.junit``` does not exist error. I have double-checked the JUnit library files, their names, and locations, but I can't seem to figure out why the package is not being found. 

<img src="labgrade.png"/>

When you see the screenshot above, I am copying the necessary junit packages over to the grade-area, which is where the compilation of junit is done. However, the error states that it is still not found. It seems like it is successfully copied as well: 

<img src="gradingarea.png"/>

Could you please provide guidance on how to resolve this issue? Is there anything else I should check or configure to ensure that the JUnit package is detected during compilation and execution?

**Detail the failure-inducing input and context. That might mean any or all of the command you're running, a test case, command-line arguments, working directory, even the last few commands you ran. Do your best to provide as much context as you can.**

Although I do not think that the java code is the problem, here is the code for TestListExamples.java: 

<img src="testexamples.png"/>
<img src="codingblocktest.png"/>

The command that I used was: 

```bash labgrade.sh https://github.com/ucsd-cse15l-f22/list-methods-corrected```

I don't think it's a problem with student submission as well, because this student submission should pass. 
          
