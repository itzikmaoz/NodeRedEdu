# Global Context, Calculating Elapsed Time

This module will show how to utilize the global context and track how many seconds have passed between random injections. This program is beneficial to those that need a global variable to track information from multiple flows. 

Video length: 2:27 minutes

### ![Link to Video](https://youtu.be/mUSxM6KTN9s)

### Nodes Needed

- 1 inject 
- 2 function nodes
- 1 delay
- 1 debug 

### Instructions

This program is based on the content created by Rodger Lea on www.noderedguide.com.

1. Wire inject > function1 > delay > function2 > debug.

<img src="https://github.ibm.com/L-Gamerman/NodeRedEducation/blob/master/Chapter%201%20-%20Getting%20Started/Screenshots/gc_flow.png">

2. Edit the first function node in the flow and type:

``` javascript 
context.global.startTime = new Date().getTime();
return msg;
```

<img src="https://github.ibm.com/L-Gamerman/NodeRedEducation/blob/master/Chapter%201%20-%20Getting%20Started/Screenshots/gc_f1.png">

3. Edit the delay node

- Action: Delay each message, random delay
- Between 1 & 5 seconds

<img src="https://github.ibm.com/L-Gamerman/NodeRedEducation/blob/master/Chapter%201%20-%20Getting%20Started/Screenshots/gc_delay.png">

4. Edit the second function node and type: 

``` javascript
var currentTime = new Date().getTime();
var timeElapsed = (currentTime - context.global.startTime);
msg.payload = "Time elapsed is: " + timeElapsed + " seconds.";
return msg;
```
<img src="https://github.ibm.com/L-Gamerman/NodeRedEducation/blob/master/Chapter%201%20-%20Getting%20Started/Screenshots/gc_f2.png">

5. Deploy 

<img src="https://github.ibm.com/L-Gamerman/NodeRedEducation/blob/master/Chapter%201%20-%20Getting%20Started/Screenshots/deploy.png">

6. Inject! 

<img src="https://github.ibm.com/L-Gamerman/NodeRedEducation/blob/master/Chapter%201%20-%20Getting%20Started/Screenshots/inject2.png">

<img src="https://github.ibm.com/L-Gamerman/NodeRedEducation/blob/master/Chapter%201%20-%20Getting%20Started/Screenshots/gc_flow_complete.png">

### Results will vary: 

<img src="https://github.ibm.com/L-Gamerman/NodeRedEducation/blob/master/Chapter%201%20-%20Getting%20Started/Screenshots/gc_result.png">

### [Next module: Loops >>](https://github.ibm.com/L-Gamerman/NodeRedEducation/tree/master/Chapter%204%20-%20Function%20Nodes/3.%20Loops)
