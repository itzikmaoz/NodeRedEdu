# Texting Weather Conditions From Node Red

This module will demonstrate how to connect to a third-party weather API and the Twilio texting API to create a program that sends the current weather conditions via SMS.

**What is Twilio?** 

Twilio is a platform that has a cloud API that easily allows developers to program voice, video, SMS, email and chat. In this module, Twilio will allow us to create a phone number to send text messages. To utilize Twilio's features, you need to download the node-red-node-twilio palette. 

**What is Weather Underground?**

Weather Underground is a weather forecast website that provides API keys for developers to work with their data. You can utilize Weather Underground in Node Red by downloading the node-red-node-weather-underground palette. We are using Weather Underground in this module because the node determines location using city and state rather than longitude and latitude coordinates.

### ![Link to Video](https://youtu.be/pfY0t6XdQXo)

Video length: 5:36 minutes

### Nodes Needed: 
- 1 Weather Underground node
- 1 Twilio node
- 1 function node
- 1 inject node
- 1 debug node

### Instructions

1. First, we need to configure the Weather Underground and Twilio nodes and get the API keys. 

2. Open a new browser and type in: https://www.wunderground.com/

<img src="https://github.ibm.com/L-Gamerman/NodeRedEducation/blob/master/Chapter%201%20-%20Getting%20Started/Screenshots/wunderground_landing.png" height="">

3. In the menu bar at the top, click on More > Weather API for Developers. 

<img src="https://github.ibm.com/L-Gamerman/NodeRedEducation/blob/master/Chapter%201%20-%20Getting%20Started/Screenshots/api_menu.png" height="">

4. In the menu bar, click "Key Settings."

<img src="https://github.ibm.com/L-Gamerman/NodeRedEducation/blob/master/Chapter%201%20-%20Getting%20Started/Screenshots/key_settings.png" height="">

5. Click create new key. 

6. Select the stratus plan and click "Purchase Key". 

<img src="https://github.ibm.com/L-Gamerman/NodeRedEducation/blob/master/Chapter%201%20-%20Getting%20Started/Screenshots/stratus.png" height="">

7. Fill in your information into the form. Click "Purchase Key". 

8. Copy down your Weather Underground API key somewhere that you can easily reference. We will be using this shortly. 

9. Open another browser window and type in: https://www.twilio.com/

10. Click "Get a free API key".

<img src="https://github.ibm.com/L-Gamerman/NodeRedEducation/blob/master/Chapter%201%20-%20Getting%20Started/Screenshots/twilio_landing.png" height="">

11. Fill out your information and sign up for an account. 

<img src="https://github.ibm.com/L-Gamerman/NodeRedEducation/blob/master/Chapter%201%20-%20Getting%20Started/Screenshots/twilio_sign_up.png" height="">

12. Navigate to your Twilio Dashboard. On the side, click the second button from the top.

<img src="https://github.ibm.com/L-Gamerman/NodeRedEducation/blob/master/Chapter%201%20-%20Getting%20Started/Screenshots/twilio_dash.png" height="">

13. On that menu, scroll down and under Developer Tools,  click Runtime.

<img src="https://github.ibm.com/L-Gamerman/NodeRedEducation/blob/master/Chapter%201%20-%20Getting%20Started/Screenshots/click_runtime.png" height="">

14. On the left menu bar, click API keys. 

<img src="https://github.ibm.com/L-Gamerman/NodeRedEducation/blob/master/Chapter%201%20-%20Getting%20Started/Screenshots/click_api.png" height="">

15. Click the plus sign <img src="https://github.ibm.com/L-Gamerman/NodeRedEducation/blob/master/Chapter%201%20-%20Getting%20Started/Screenshots/plus.png" width="50"> to create a new API key. 

16. Pick a friendly name for your own reference and click "Create API Key".

<img src="https://github.ibm.com/L-Gamerman/NodeRedEducation/blob/master/Chapter%201%20-%20Getting%20Started/Screenshots/new_api.png" height="">

17. **These credentials will not be shown again** So, copy the credentials down into a place that you can reference easily.

18. On the left, click this menu <img src="https://github.ibm.com/L-Gamerman/NodeRedEducation/blob/master/Chapter%201%20-%20Getting%20Started/Screenshots/twilio_menu.png" width="50">

19. Navigate to "Phone Numbers" in the Super Network section. 

<img src="https://github.ibm.com/L-Gamerman/NodeRedEducation/blob/master/Chapter%201%20-%20Getting%20Started/Screenshots/phone.png" height="500">

20. Click "Get a number now". Complete the form and copy down your phone number with your other credentials. 

21. Navigate to your Node Red workspace. 

22. To download the Weather Underground node palette, click the 3 bar menu button at the top right corner. <img src="https://github.ibm.com/L-Gamerman/NodeRedEducation/blob/master/Chapter%201%20-%20Getting%20Started/Screenshots/menu_icon.png" width="50">

23. Click "Manage palettes".

<img src="https://github.ibm.com/L-Gamerman/NodeRedEducation/blob/master/Chapter%201%20-%20Getting%20Started/Screenshots/manage.png" height="500">

24. Click the install tab.

<img src="https://github.ibm.com/L-Gamerman/NodeRedEducation/blob/master/Chapter%201%20-%20Getting%20Started/Screenshots/install_tab.png" height="">

25. Type in: node-red-node-weather-underground. Press the install button next to the package. Click close. 

<img src="https://github.ibm.com/L-Gamerman/NodeRedEducation/blob/master/Chapter%201%20-%20Getting%20Started/Screenshots/wu_palette.png" height="">

26. Pull out an inject node, wunderground node with input and outputs, function node, twilio node and a debug node. Wire them together like so:

<img src="https://github.ibm.com/L-Gamerman/NodeRedEducation/blob/master/Chapter%201%20-%20Getting%20Started/Screenshots/wu_text_flow.png" height="">

27. Edit the inject node and name it "Current weather alert".

<img src="https://github.ibm.com/L-Gamerman/NodeRedEducation/blob/master/Chapter%201%20-%20Getting%20Started/Screenshots/wu_inject.png" height="500">

28. Edit the wunderground node. 

  - Enter the city and state that you want the weather for. 
  - Copy & paste in your Weather Underground API key. 

<img src="https://github.ibm.com/L-Gamerman/NodeRedEducation/blob/master/Chapter%201%20-%20Getting%20Started/Screenshots/wu_node.png" height="">

29. Edit the function node and in the body, type: 

``` javascript
msg.payload = msg.payload.description;
return msg;
```
<img src="https://github.ibm.com/L-Gamerman/NodeRedEducation/blob/master/Chapter%201%20-%20Getting%20Started/Screenshots/wu_function.png" height="">

30. Edit the Twilio node. 

  - Service: External service
  - Twilio: Add new twilio-api... (click the pen symbol to the right)

<img src="https://github.ibm.com/L-Gamerman/NodeRedEducation/blob/master/Chapter%201%20-%20Getting%20Started/Screenshots/twilio1.png" height="">

  - Account SID: Copy & paste your Twilio SID key (from the API key section we created earlier)
  - From: Use the Twilio phone number that we generated earlier.
  - Token: Copy & paste your Twilio secret into this textbox. 
  - Click add
  
<img src="https://github.ibm.com/L-Gamerman/NodeRedEducation/blob/master/Chapter%201%20-%20Getting%20Started/Screenshots/twilio2.png" height="">

  - In the SMS box, type in the number you want to text. Make sure to put the + sign and your country code before your number.

31. Click deploy.

<img src="https://github.ibm.com/L-Gamerman/NodeRedEducation/blob/master/Chapter%201%20-%20Getting%20Started/Screenshots/deploy.png"> 

32. Inject!

<img src="https://github.ibm.com/L-Gamerman/NodeRedEducation/blob/master/Chapter%201%20-%20Getting%20Started/Screenshots/inject.png">

### Result

A text should be sent to the phone specified with the current weather conditions. 

### Sending Texts of the Forecast

If you wanted to change the flow to send messages for the forecast for the following day, edit the function node and replace the code with this: 

``` javascript
msg.payload = msg.payload.forecast;
return msg;
```
### [Next chapter: Chapter 5 - Watson & Cognitive API Nodes >>](https://github.ibm.com/L-Gamerman/NodeRedEducation/tree/master/Chapter%205%20-%20Watson%20%26%20Cognitive%20API%20Nodes)
