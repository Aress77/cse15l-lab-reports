# Part 1

For the program, I used the `Server.java` file provided in class as a basis.

<img width="814" alt="Screen Shot 2024-04-21 at 3 07 52 PM" src="https://github.com/Aress77/cse15l-lab-reports/assets/122946762/be3a0415-761c-42dd-a278-5d74bb818e81">

<br/><br/> 

## `/add-message?s=Hello&user=jpolitz`

<img width="532" alt="Screen Shot 2024-04-21 at 3 40 33 PM" src="https://github.com/Aress77/cse15l-lab-reports/assets/122946762/8766af35-5fa3-4af2-b44e-f8783f5c72f3">

### Which methods in your code are called?
The `public String handleRequest(URI url)` method is called. 
### What are the relevant arguments to those methods, and the values of any relevant fields of the class?
Relevant arguments: <br/>
`URI url`: The URI object passed to the handleRequest method. The request should be`/add-message?s=Hello&user=jpolitz`.<br/><br/> 
Relevant fields: <br/>
`chat`: Stores the user and chat messages. <br/><br/> 
Values of any relevant fields: Initial value for `chat` is `""`. <br/>
### How do the values of any relevant fields of the class change from this specific request? If no values got changed, explain why.
When we `/add-message` with `s=message` and `user=username` parameters, it will append the username and message user inputed to the String `chat`. In this case, we have `s=Hello` and `user=jpolitz`. The updated `chat` will contain `"jpolitz: Hello \n"`. <br/><br/> 
## `/add-message?s=How are you&user=yash`
<img width="626" alt="Screen Shot 2024-04-21 at 3 11 29 PM" src="https://github.com/Aress77/cse15l-lab-reports/assets/122946762/c821fb2c-375c-426d-a685-28e067e7ad8e">

### Which methods in your code are called?
The `public String handleRequest(URI url)` method is called. 
### What are the relevant arguments to those methods, and the values of any relevant fields of the class?
Relevant arguments: <br/>
`URI url`: The URI object passed to the handleRequest method. The request we are adding should be`/add-message?s=How%20are%20you&user=yash`.<br/><br/> 
Relevant fields: <br/>
`chat`: Stores the user and chat messages. <br/><br/> 
Values of any relevant fields: Current value for `chat` is `"jpolitz: Hello \n"`.
### How do the values of any relevant fields of the class change from this specific request? If no values got changed, explain why.
 When we `/add-message` with `s=message` and `user=username` parameters, it will append the username and message user inputed to the String `chat`. In this case, we have `s=How%20are%20you` and `user=yash`. `chat` will now contain `"jpolitz: Hello \n yash: How are you \n"`.<br/><br/> 

# Part 2

### 1. 
<img width="345" alt="Screen Shot 2024-04-21 at 5 42 28 PM" src="https://github.com/Aress77/cse15l-lab-reports/assets/122946762/0f2ce312-f046-4013-8ad3-1b5ff8ca94c3">

### 2. 
<img width="384" alt="Screen Shot 2024-04-21 at 6 59 19 PM" src="https://github.com/Aress77/cse15l-lab-reports/assets/122946762/3842fcaf-ad23-41bd-a022-a8e54a575216">

<img width="793" alt="Screen Shot 2024-04-21 at 6 55 35 PM" src="https://github.com/Aress77/cse15l-lab-reports/assets/122946762/53ed42c1-f766-41bc-8350-59ce98c6b889">

### 3.
In weeks 2 and 3, I learned how to use SSH keys to login remote server without password on my laptop. I also learned how to build, run and make changes to a server in terminal. 
