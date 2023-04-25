# Part 1

### This is the code for the StringServer: 
![StringServer](StringServer.png)

### /add-message?s=Hello
![Hello](helloadd.png)

1. **Which methods in your code are called?**

> When you put /add-message?s=Hello to the URL, the handleRequest method of the Handler class is called.  

2. **What are the relevant arguments to those methods, and the values of any relevant fields of the class?**

> The relevant argument to this method is the URI object representing the requested URL. The message field of the Handler class is also relevant. 

3. **How do the values of any relevant fields of the class change from this specific request? If no values got changed, explain why.**

> First of all, the url changes from merely having localhost with port number to having /add-message?s=Hello. The value of message is changed from "" to "Hello". **It is because..** Inside the handleRequest method, the code checks if the URL path is equal to /add-message. If it is, the query string "s=Hello" is extracted from the URL, and the message field of the Handler class is updated with the new message. If the message field was empty before, it is assigned the value of "Hello". 

### /add-message?s=How are you
![How are you](howareyouadd.png)

1. **Which methods in your code are called?**

> Similarly, putting /add-message?s=How are you to the URL will call the handleRequest method of the Handler class. 

2. **What are the relevant arguments to those methods, and the values of any relevant fields of the class?**

> The relevant argument to this method is the URI object representing the requested URL. The message field of the Handler class is also relevant. 

3. **How do the values of any relevant fields of the class change from this specific request? If no values got changed, explain why.**

> Likewise, the url changes from /add-message?s=Hello to /add-message?s=How%are%you. The space in between words are changed to %. It prints "Hello \n How are you" on the screen. The reason why it prints "Hello \n How are you" instead of just "How are you" is because the message variable already contains the value "Hello" from the previous request. So when the second request is made with the query parameter s=How are you, the handleRequest method concatenates it to the existing message with a newline character \n, resulting in the message "Hello\nHow are you".

# Part 2

1. **Failure Inducing Code**

```
static List<String> filter(List<String> list, StringChecker sc) {
    List<String> result = new ArrayList<>();
    for(String s: list) {
      if(sc.checkString(s)) {
        result.add(0,s);
      }
    }
    return result;
 }
```

```
@Test //Does not pass the test
public void filterTest() {
    StringChecker sc = new StringCheck("a");
    List<String> list = new ArrayList<>();
    list.add(null);
    list.add("b");
    list.add("a");
    List<String> list2 = new ArrayList<>();
    list2.add("b");
    assertEquals(list2, ListExamples.filter(list, sc));
  }
```

![symptom](symptom.png)

As shown in the screenshot above, the test results in NullPointerException. This gives error because the add method does not address the case for a null element, therefore the code should be fixed so that it addresses the input. The fixed method below should work because it checks for elements in the list that are null. It checks if the list itself is null, and if the StringChecker element is null as well. 

2. **Fixed Method**

```
static List<String> filter(List<String> list, StringChecker sc) {
    List<String> result = new ArrayList<>();
    if (list == null) {
      return result;
    }
    if (sc == null) {
      return result;
    }
    for(String s: list) {
      if (s == null) {
        continue;
      }
      if(sc.checkString(s)) {
        result.add(s);
      }
    }
    return result;
  }
```

**Now, this would work:**
```
@Test //This passes the test
  public void filterTest() {
    StringChecker sc = new StringCheck("a");
    List<String> list = new ArrayList<>();
    list.add(null);
    list.add("b");
    list.add("a");
    List<String> list2 = new ArrayList<>();
    list2.add("b");
    assertEquals(list2, ListExamples.filter(list, sc));
  }
```




