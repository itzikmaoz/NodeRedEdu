# Adding to the Global Context

This module will demonstrate how to add to the global context, which allows for multiple nodes in different flows to access the global context data. 

Video length: 2:18 minutes

### ![Link to Video](https://youtu.be/O9IjB-d-ow4)

<h3>Nodes Needed</h3>

- 2 inject nodes
- 2 debug nodes
- 2 function nodes

<h3>Instructions</h3>

1. Wire inject > function > debug twice.

<img src="https://github.ibm.com/L-Gamerman/NodeRedEducation/blob/master/Chapter%201%20-%20Getting%20Started/Screenshots/flow_w:o_names.png" width="">

2. Click on the first function node.

  - Name: part 1
  - Function: 
 
``` javascript
context.global.hello = function() { return "A house divided " };
msg.payload = context.global.hello();
return msg;
```

<img src="https://github.ibm.com/L-Gamerman/NodeRedEducation/blob/master/Chapter%201%20-%20Getting%20Started/Screenshots/function_part1.png" width="400">

3. Click on the second function node.

  - Name: part 2
  - Function:
  
``` javascript
msg.payload = context.global.hello() + "against itself cannot stand.";
return msg;
```

<img src="https://github.ibm.com/L-Gamerman/NodeRedEducation/blob/master/Chapter%201%20-%20Getting%20Started/Screenshots/function_part2.png" width="400">

4. Deploy and inject both flows. 

<img src="https://github.ibm.com/L-Gamerman/NodeRedEducation/blob/master/Chapter%201%20-%20Getting%20Started/Screenshots/flow_w_names.png" width="">

### Result: 

The second flow adds a string to the previous payload, using the global context feature.

<img src="https://github.ibm.com/L-Gamerman/NodeRedEducation/blob/master/Chapter%201%20-%20Getting%20Started/Screenshots/Global_context_result.png" width="400">

### [Next module: Global Context, Calculating Elapsed Time >>](https://github.ibm.com/L-Gamerman/NodeRedEducation/blob/master/Chapter%204%20-%20Function%20Nodes/2.%20Global%20Context/Global%20Context%2C%20Calculating%20Elapsed%20Time.md)
