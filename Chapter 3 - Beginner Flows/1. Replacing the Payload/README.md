<h1>Replacing the Payload</h1>

This module will explain how to create a flow that replaces the payload of a node. Replacing the information in a node's payload could be useful if the variable is based on changing sensor or database data.  

Video length: 1 minute

### ![Link to Video](https://youtu.be/sXxLIrdsw3U)

### Nodes Needed: 
- 1 inject node
- 1 function node
- 1 debug node 

### Instructions
1. Drag out an inject node onto the workspace. In the payload of the inject node, type in a message. 

<img src="../Chapter%201%20-%20Getting%20Started/Screenshots/will_this_change%3F.png" width="400">

2. Pull out a function node. Edit the function node and type in the body: 

``` javascript
var newMessage = {payload: "replaced msg"};
return newMessage;
```

<img src="../Chapter%201%20-%20Getting%20Started/Screenshots/function_replaced.png" width="400">

3. Wire together the inject -> function node -> debug node. 

![](../Chapter%201%20-%20Getting%20Started/Screenshots/replaced_flow.png)

4. Click deploy.

<img src="../Chapter%201%20-%20Getting%20Started/Screenshots/deploy.png">

5. Inject.

<img src="../Chapter%201%20-%20Getting%20Started/Screenshots/inject2.png">

### Result

"replaced msg" 

![](../Chapter%201%20-%20Getting%20Started/Screenshots/replaced_payload.png)

### [Next module: Displaying Sentiment Score with News >>](../Chapter%203%20-%20Beginner%20Flows/2.%20Displaying%20Sentiment%20Score%20With%20News)
