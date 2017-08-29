<h1>Context in Function Nodes</h1>

This module will explain how to use the context feature in Node Red. The context feature allows for multiple nodes, in the same flow, to share the context's data. 

Video length: 1:26 minutes

### ![Link to Video](https://youtu.be/McCZvBWVCRg)

<h3>Nodes Needed</h3>

- 1 inject 
- 1 debug 
- 1 function 

<h3>Instructions</h3> 

1. Wire inject > function > debug. 

<img src="../Chapter%201%20-%20Getting%20Started/Screenshots/count_flow2.png" width=""> 

2. Edit the function node and type: 

``` javascript
if (!context.value){
    context.value = 0;
}
context.value += 1;
msg.count = context.value;
return msg;
```

<img src="../Chapter%201%20-%20Getting%20Started/Screenshots/count_function.png" width="400"> 

3. Edit the debug node and change the output from msg.payload to complete msg object. 

<img src="../Chapter%201%20-%20Getting%20Started/Screenshots/count_debug.png" width="400">

4. Deploy.

<img src="../Chapter%201%20-%20Getting%20Started/Screenshots/deploy.png" width=""> 

5. Inject 4 times. 

<img src="../Chapter%201%20-%20Getting%20Started/Screenshots/count_final_flow.png" width=""> 

### Result

The context feature is counting the amount of injections in the current deployment in the "count" variable. To refresh the count, re-deploy the flow. 

<img src="../Chapter%201%20-%20Getting%20Started/Screenshots/count_result.png" height="350"> 

### [Next module: Global Context >>](../Chapter%204%20-%20Function%20Nodes/2.%20Global%20Context)
