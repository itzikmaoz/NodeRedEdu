<h1> Displaying Sentiment Score with News </h1>

This module will explain how to import news data and apply sentiment analysis to the headlines.

Video length: 2 minutes

### ![Link to Video](https://youtu.be/8OBIJiq3jnw)

<h3>Nodes Needed</h3>

- 1 feedparse node
- 1 sentiment node
- 2 debug nodes

<h3>Instructions</h3>
1. Pull out a feedparse node onto the workspace.

<img src="https://github.ibm.com/L-Gamerman/NodeRedEducation/blob/master/Chapter%201%20-%20Getting%20Started/Screenshots/feedparse_node.png">

2. In the feedparse node, add the xml link of your favorite news outlet in the feed url text box.

  - If you enjoy CNN, the XML link is here: http://rss.cnn.com/rss/cnn_topstories.rss
  
3. Refresh the node every 2 minutes and name it CNN. 

<img src="https://github.ibm.com/L-Gamerman/NodeRedEducation/blob/master/Chapter%201%20-%20Getting%20Started/Screenshots/feedparse.png" width="400">

4. Attach a debug node and the sentiment node to the CNN node. 

<img src="https://github.ibm.com/L-Gamerman/NodeRedEducation/blob/master/Chapter%201%20-%20Getting%20Started/Screenshots/sentiment_node.png">

<img src="https://github.ibm.com/L-Gamerman/NodeRedEducation/blob/master/Chapter%201%20-%20Getting%20Started/Screenshots/debug.png">

5. Connect the sentiment node to the second debug node. 

<img src="https://github.ibm.com/L-Gamerman/NodeRedEducation/blob/master/Chapter%201%20-%20Getting%20Started/Screenshots/sentiment_news_flow.png" width="400">

6. In the second debug node, change the output from msg.payload to msg.sentiment

<img src="https://github.ibm.com/L-Gamerman/NodeRedEducation/blob/master/Chapter%201%20-%20Getting%20Started/Screenshots/sentiment_debug.png" width="400">

7. Deploy.

<img src="https://github.ibm.com/L-Gamerman/NodeRedEducation/blob/master/Chapter%201%20-%20Getting%20Started/Screenshots/deploy.png">

### Result

<img src="https://github.ibm.com/L-Gamerman/NodeRedEducation/blob/master/Chapter%201%20-%20Getting%20Started/Screenshots/sentiment_news_result.png" height="400">

<h3>Sentiment Rubric</h3>

- If the number larger than zero = positive 

- If the number is zero = neutral 

- If the number less than zero = negative 

### [Next module: Changing the Sentiment Score to Words >>](https://github.ibm.com/L-Gamerman/NodeRedEducation/tree/master/Chapter%203%20-%20Beginner%20Flows/3.%20Changing%20the%20Sentiment%20Score%20to%20Words)
