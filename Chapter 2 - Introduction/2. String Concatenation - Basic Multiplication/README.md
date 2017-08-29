<h1>String Concatenation & Basic Multiplication</h1>

This module will explain how to concatenate strings and perform multiplication.

Video length: 1:36 minutes

### ![Link to Video](https://youtu.be/dI39ExnvT8o)

<h3>Nodes Needed:</h3>

- 1 inject node
- 1 function node
- 1 debug node

### Instructions
 
1. Drag out an inject node onto the workspace and double click to edit. 
2. Click on the payload "timestamp".

<img src="https://github.ibm.com/L-Gamerman/NodeRedEducation/blob/master/Chapter%201%20-%20Getting%20Started/Screenshots/timestamp.png" height="500">

3. Change the type to string.

<img src="https://github.ibm.com/L-Gamerman/NodeRedEducation/blob/master/Chapter%201%20-%20Getting%20Started/Screenshots/string.png" height="500">

4. Type "Welcome" in the payload text box. 

![](https://github.ibm.com/L-Gamerman/NodeRedEducation/blob/master/Chapter%201%20-%20Getting%20Started/Screenshots/welcome.png)

5. Click done
6. Drag out a function node and double click on the function node to edit. 
7. Name the node "adding text".
8. In the function section, type: 

``` javascript
msg.payload += " to Node Red function nodes.";
return msg;
```

![](https://github.ibm.com/L-Gamerman/NodeRedEducation/blob/master/Chapter%201%20-%20Getting%20Started/Screenshots/adding_text.png)

9. Click done. 
10. Wire the inject node -> function node -> debug node. 

![](https://github.ibm.com/L-Gamerman/NodeRedEducation/blob/master/Chapter%201%20-%20Getting%20Started/Screenshots/welcome_flow.png)

11. Click deploy.

<img src="https://github.ibm.com/L-Gamerman/NodeRedEducation/blob/master/Chapter%201%20-%20Getting%20Started/Screenshots/deploy.png">

12. Inject.

<img src="https://github.ibm.com/L-Gamerman/NodeRedEducation/blob/master/Chapter%201%20-%20Getting%20Started/Screenshots/inject.png">

#### Result

"Welcome to Node Red function nodes." 

![](https://github.ibm.com/L-Gamerman/NodeRedEducation/blob/master/Chapter%201%20-%20Getting%20Started/Screenshots/payload.png)

### Multiplication Instructions

1. Modify the inject node by changing the type to "number" and in the text box, type 5.

<img src="https://github.ibm.com/L-Gamerman/NodeRedEducation/blob/master/Chapter%201%20-%20Getting%20Started/Screenshots/5.png" width="400">

2. Edit the function node, 

 - Change the name to "multiplying".
 - In the function body, delete the old content and instead type: 

``` javascript
msg.payload *= 5;
return msg;
```

<img src="https://github.ibm.com/L-Gamerman/NodeRedEducation/blob/master/Chapter%201%20-%20Getting%20Started/Screenshots/multiplying.png" width="400">

3. Click deploy.

<img src="https://github.ibm.com/L-Gamerman/NodeRedEducation/blob/master/Chapter%201%20-%20Getting%20Started/Screenshots/deploy.png">

4. Inject.

<img src="https://github.ibm.com/L-Gamerman/NodeRedEducation/blob/master/Chapter%201%20-%20Getting%20Started/Screenshots/inject2.png">

![](https://github.ibm.com/L-Gamerman/NodeRedEducation/blob/master/Chapter%201%20-%20Getting%20Started/Screenshots/multiplication_flow.png)

### Result: 25 

![](https://github.ibm.com/L-Gamerman/NodeRedEducation/blob/master/Chapter%201%20-%20Getting%20Started/Screenshots/25.png)

### [Next chapter: Chapter 3 - Beginner Flows >>](https://github.ibm.com/L-Gamerman/NodeRedEducation/tree/master/Chapter%203%20-%20Beginner%20Flows)
