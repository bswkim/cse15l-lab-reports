### This is the code for the StringServer: 
![StringServer](StringServer.png)

### /add-message?s=Hello
![Hello](helloadd.png)

1. **Which methods in your code are called?**

> When you put /add-message?s=Hello to the URL, the handleRequest method of the Handler class is called. 

2. **What are the relevant arguments to those methods, and the values of any relevant fields of the class?**

> The relevant argument to this method is the URI object representing the requested URL. The message field of the Handler class is also relevant. 

3. **How do the values of any relevant fields of the class change from this specific request? If no values got changed, explain why.**

> The value of message is changed from "" to "Hello". **It is because..** Inside the handleRequest method, the code checks if the URL path is equal to /add-message. If it is, the query string "s=Hello" is extracted from the URL, and the message field of the Handler class is updated with the new message. If the message field was empty before, it is assigned the value of "Hello". 

### /add-message?s=How are you
![How are you](howareyouadd.png)

1. **Which methods in your code are called?**

> Similarly, putting /add-message?s=How are you to the URL will call the handleRequest method of the Handler class. 

2. **What are the relevant arguments to those methods, and the values of any relevant fields of the class?**

> The relevant argument to this method is the URI object representing the requested URL. The message field of the Handler class is also relevant. 

3. **How do the values of any relevant fields of the class change from this specific request? If no values got changed, explain why.**

> It prints "Hello \n How are you" on the screen. The reason why it prints "Hello \n How are you" instead of just "How are you" is because the message variable already contains the value "Hello" from the previous request. So when the second request is made with the query parameter s=How are you, the handleRequest method concatenates it to the existing message with a newline character \n, resulting in the message "Hello\nHow are you".






