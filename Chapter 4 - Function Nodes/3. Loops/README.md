# Loops 

This module shows how to create a loop in Node Red.

Video length: 1:27 minutes

### ![Link to Video](https://youtu.be/e5eSZ8jXGPA)

### Nodes Needed
- 1 inject
- 1 debug
- 1 function

### Instructions

1. Wire an inject > function > debug. 

<img src="../Chapter%201%20-%20Getting%20Started/Screenshots/loop_flow.png">

2. Edit the function node and type: 

**If you copy and paste this code into the text box, the quotation marks will not format correctly and will produce an error. To fix this, please type in the code for var letterList.**

``` javascript
var msgList = [];
var letterList = [“a”, “b”, “c”, “d”, “e”];
for (var i = 0; i < 5; i++) {
  msgList.push({payload:letterList[i]});
}
return [msgList]; 
```

<img src="../Chapter%201%20-%20Getting%20Started/Screenshots/loop_function.png" height="400">

3. Click deploy.

<img src="../Chapter%201%20-%20Getting%20Started/Screenshots/deploy.png">

4. Inject. 

<img src="../Chapter%201%20-%20Getting%20Started/Screenshots/inject2.png">

### Result: 

<img src="../Chapter%201%20-%20Getting%20Started/Screenshots/loop_result.png">

### [Next module: Parsing HTML Data From a Website >>](https://github.ibm.com/L-Gamerman/NodeRedEducation/edit/master/Chapter%204%20-%20Function%20Nodes/4.%20Parsing%20HTML%20Data%20From%20a%20Website/README.md)
