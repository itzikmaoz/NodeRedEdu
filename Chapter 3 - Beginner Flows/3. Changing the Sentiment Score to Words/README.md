<h1>Changing the Sentiment Score to Words</h1> 

This module will explain how to change the sentiment algorithm output from numbers to words, making the output more human readable.

Video length: 3 minutes

### ![Link to Video](https://youtu.be/YVD3nnRsod0)

<h3>Nodes Needed</h3>

- 1 feedparse node
- 1 sentiment node
- 1 debug node
- 1 switch node
- 3 change nodes

<h3>Instructions</h3> 
1. Read the previous document, "Displaying Sentiment Score with News" or import the SentimentScoreNum.flow into Node Red to create the precursor flow, including the set up for the feedparse + sentiment nodes. 


To import code into Node Red:
- Click the three bar menu in the top right corner. <img src="https://github.ibm.com/L-Gamerman/NodeRedEducation/blob/master/Chapter%201%20-%20Getting%20Started/Screenshots/menu_icon.png" width="30">
- Import > Clipboard
- Paste code into the text box. 
- Click import.

<img src="https://github.ibm.com/L-Gamerman/NodeRedEducation/blob/master/Chapter%201%20-%20Getting%20Started/Screenshots/sentiment_news_flow.png" width="400"> 

2. Pull out a switch node onto the workspace.

<img src="https://github.ibm.com/L-Gamerman/NodeRedEducation/blob/master/Chapter%201%20-%20Getting%20Started/Screenshots/switch.png">

3. Edit the switch node.

    - Name: comparison 
    - Property: msg.sentiment.score
    - Condition 1: <, integer zero 
    - Condition 2: ==, integer zero
    - Condition 3: >, integer zero
    
<img src="https://github.ibm.com/L-Gamerman/NodeRedEducation/blob/master/Chapter%201%20-%20Getting%20Started/Screenshots/0.jpg" width="400"> 

4. Remove the wire from the sentiment node to the debug node. Click on the wire (the color will change to orange) and press delete.

5. Attach the sentiment to the comparison node. 

6. Change node 1, the node that attaches to the first output:

<img src="https://github.ibm.com/L-Gamerman/NodeRedEducation/blob/master/Chapter%201%20-%20Getting%20Started/Screenshots/node1.png">

   - Name: neg
   - Set msg.payload to "Negative" 
   - Attach to the 1st output circle of the comparison node. 
    
<img src="https://github.ibm.com/L-Gamerman/NodeRedEducation/blob/master/Chapter%201%20-%20Getting%20Started/Screenshots/change_node_neg.png" width="400"> 

7. Change node 2, the node that attaches to the second output from comparison: 

<img src="https://github.ibm.com/L-Gamerman/NodeRedEducation/blob/master/Chapter%201%20-%20Getting%20Started/Screenshots/node2.png">

   - Name: neutral
   - Set msg.payload to "Neutral" 
   - Attach to the 2nd output circle of the comparison node. 
    
<img src="https://github.ibm.com/L-Gamerman/NodeRedEducation/blob/master/Chapter%201%20-%20Getting%20Started/Screenshots/change_node_neutral.png" width="400"> 

8. Change node 3, the node that attaches to bottom output from comparison: 

<img src="https://github.ibm.com/L-Gamerman/NodeRedEducation/blob/master/Chapter%201%20-%20Getting%20Started/Screenshots/node3.png">

   - Name: pos
   - Set msg.payload to "Positive" 
   - Attach to the 3rd output circle of the comparison node. 
    
<img src="https://github.ibm.com/L-Gamerman/NodeRedEducation/blob/master/Chapter%201%20-%20Getting%20Started/Screenshots/change_node_pos.png" width="400"> 

9. Connect all the change nodes to a debug node. 

<img src="https://github.ibm.com/L-Gamerman/NodeRedEducation/blob/master/Chapter%201%20-%20Getting%20Started/Screenshots/sentiment_words_flow.png"> 

10. Deploy.

<img src="https://github.ibm.com/L-Gamerman/NodeRedEducation/blob/master/Chapter%201%20-%20Getting%20Started/Screenshots/deploy.png">


### Result

Results will vary as the CNN's top new stories change quick, but here's my result: 

<img src="https://github.ibm.com/L-Gamerman/NodeRedEducation/blob/master/Chapter%201%20-%20Getting%20Started/Screenshots/sentiment_words_result.png" height="500"> 

### [Next chapter: Chapter 4 - Function Nodes >>](https://github.ibm.com/L-Gamerman/NodeRedEducation/tree/master/Chapter%204%20-%20Function%20Nodes)
