# Parsing HTML Data From a Website

This module will explain how to parse data from a website and track the amount of times that the word "compose" is used in the paragraph tags. 

Video length: 3:26 minutes

### ![Link to Video](https://youtu.be/iInMTIL_ViA)

### Nodes Needed

- 1 inject
- 1 http request
- 1 html 
- 2 debugs
- 1 function 

<h3>Instructions</h3> 

1. Pull out an inject node and a http request node (the node with an input *and* an output) node onto the workspace.

<img src="../Chapter%201%20-%20Getting%20Started/Screenshots/inject.png">

<img src="../Chapter%201%20-%20Getting%20Started/Screenshots/http_request.png">

2. Edit the http request node and set the method to GET. 

  - Method: GET
  - URL: https://www.compose.com/articles/interloop-making-the-most-of-compose/?cm_mc_uid=41838085138814985679915&cm_mc_sid_50200000=&cm_mc_sid_52640000=
  - Return: UTF-8 string
  - Name: accessing the site
  
<img src="../Chapter%201%20-%20Getting%20Started/Screenshots/HTML_http.png" width="400"> 

3. Pull out a HTML node. 

<img src="../Chapter%201%20-%20Getting%20Started/Screenshots/html_node.png">

4. Edit the HTML node 

  - Selector: p 
  - Output: the html content of the elements, as a single message containing an array
 
<img src="../Chapter%201%20-%20Getting%20Started/Screenshots/HTML_node.png" width="400"> 

5. Drag out a function node and edit it.

  - Name: iterating thru p tags
  - Body: 

``` javascript
if (!context.count) {
   context.count = 0; 
}
for (var i = 0; i < 20; i++) {
   if(msg.payload[i].includes("Compose")){
      context.count++;
   }
}
msg.payload = context.count;
return msg;
```

<img src="../Chapter%201%20-%20Getting%20Started/Screenshots/HTML_function.png" width="400"> 

6. Attach a debug node to the HTML node and another debug node after the function node. 

7. Wire inject -> http request -> html -> debug & function -> debug

<img src="../Chapter%201%20-%20Getting%20Started/Screenshots/HTML_flow.png"> 

8. Click deploy.

<img src="../Chapter%201%20-%20Getting%20Started/Screenshots/deploy.png">

9. Inject. 

<img src="../Chapter%201%20-%20Getting%20Started/Screenshots/inject.png">

### Result

The first element on the debug screen is the parsed p tags information from the website. The second element is the number of times the word "compose" is mentioned in the p tags.

<img src="../Chapter%201%20-%20Getting%20Started/Screenshots/HTML_result.png" width="400"> 

This flow can be used to parse other HTML tags. To modify this code to parse other information: 

- Change the URL in the http request node (go back to step 1, bullet point 2)
- Change the selector in the HTML node (go back to step 2, bullet point 1)

### [Next module: Texting Weather Conditions From Node Red >>](../Chapter%204%20-%20Function%20Nodes/5.%20Texting%20Weather%20Conditions)
