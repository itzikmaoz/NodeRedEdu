# Lights on the SenseHat

This module will explain how to change the lights on a SenseHat. 

### Nodes Needed
-	1 SenseHat In
-	1 SenseHat Out
-	2 delay nodes
-	1 function

### Flow Instructions

1. Wire SenseHat In -> delay -> function -> delay -> SenseHat Out.

<img src="https://github.ibm.com/L-Gamerman/NodeRedEducation/blob/master/Chapter%201%20-%20Getting%20Started/Screenshots/sense_flow.png" height="">

2. In the both delay nodes: 

  - Action: Delay each message, Fixed delay
  - For: 2 seconds
  - This will slow down the message rate so the colors will not change too quickly.
  
  <img src="https://github.ibm.com/L-Gamerman/NodeRedEducation/blob/master/Chapter%201%20-%20Getting%20Started/Screenshots/fixed_delay.png" height="500">

3. In the function node, set the msg.payload = "whatever_colors_you_want".

4. To learn more about the colors, read the instructions below.

### Light Instructions

To set the lights on the Pi’s SenseHat:

Set the values in the msg.payload, ex. “x, y, color”; 
- X and y must either be a value from 0 to 7, since the SenseHat is 8x8.
- The origin of the Raspberry Pi is the corner to the left of the microSD card. 
- To indicate the entire row or column, use a * in place of the x or y value.
  - ex. msg.payload = "*, 4, green";
  - This will fill the entire x column on in the 4th row on the y axis. 
- If you want to select a range of lights, select the numbers by using a dash ex. 2-4.
  - ex. msg.payload = "1-2,4,green";
  - This will select the 2nd and 3rd spots on the x axis on the 4th row on the y axis. 
- The color at the end of the payload are going to be the ones with the highest priority. So, if you overlap... 
  - ex. msg.payload = "*, *,blue,3-4,3-4,yellow";
  - Result: Full blue screen with a 2x2 yellow box in the middle
  - ex. msg.payload = "3-4,3-4,yellow, *, *,blue";
  - Result: Full blue screen
- If the SenseHat does not recognize the proper color format, it will display the payload on the screen. 
- To display words on the screen, simply write the message you want to print in the msg.payload


The following message properties can be used to customize the appearance of the text:

-	msg.color - the colour of the text, default: white
-	msg.background - the colour of the background, default: off
-	msg.speed - the scroll speed. A value in the range 1 (slower) to 5 (faster), default: 3

Common colors: 

- red = (255, 0, 0)
- orange = (255, 165, 0)
- yellow = (255, 255, 0)
- green = (0, 255, 0)
- blue = (0, 0, 255)
- purple = (148,0,211)
- white = (255,255,255)
- black/off = (0,0,0)
- pink = (255,105, 180)

**Option 1:** HTML color name
msg.payload = “x, y, <color_name>”; 
-	If you are going to type out the name of the color, has to be one of the common colors listed above.

**Option 2:** RGB color value
msg.payload = “x, y, 255, 105, 180”;
-	Result: pink lights

**Option 3:** Hex color value
msg.payload = “x, y, #xxxXXX”

## Sample programs

![Video of the lights on the Pi](https://youtu.be/arS2r8znAxU)

**Sets the four corners to red, green, yellow and blue**
``` javascript 
msg.payload = “0,0,red,0,7,#00ff00,7,7,yellow,7,0,0,0,255”;
return msg;
```

**3-pixel wide purple columns**
``` javascript 
msg.payload = “4-6,*,purple”
return msg;
```

**To set the whole screen a certain color**
``` javascript 
*,*,<color>
return msg;
```

**Rainbow Diagonal Line**
``` javascript 
msg.payload = “0-1,0-1,red,1-2,1-2,orange,2-3,2-3,yellow,3-4,3-4,green,4-5,4-5,blue,5-6,5-6,purple,6-7,6-7,white";
return msg;
```

**Double Rainbow Diagonal Lines**
``` javascript 
msg.payload = "0-1,0-1,red,1-2,1-2,orange,2-3,2-3,yellow,3-4,3-4,green,5-6,5-6,purple,6-7,6-7,white,0-1,6-7,red,1-2,5-6,orange,2-3,4-5,yellow,5-6,1-2,purple,6-7,0-1,white,4-5,4-5,blue,4-5,2-3,blue,3-4,3-4,green";
return msg;
```

**4 Colored Screen**
``` javascript 
msg.payload = "0-7,0-7,purple,1-6,1-6,blue,2-5,2-5,green,3-4,3-4,yellow";
return msg;
```

**Setting the whole screen to random colors**
``` javascript 
var color1 = Math.floor(Math.random() * 255);
var color2 = Math.floor(Math.random() * 255);
var color3 = Math.floor(Math.random() * 255);
var fullColor = color1 + "," + color2 + "," + color3;
msg.payload = "*,*," + fullColor;
return msg;
```

**Setting 2 random colors to the screen**
``` javascript 
var color1 = Math.floor(Math.random() * 255);
var color2 = Math.floor(Math.random() * 255);
var color3 = Math.floor(Math.random() * 255);
var middleColor = color1 + "," + color2 + "," + color3;
var outsideColor = color3 + "," + color1 + "," + color2;
msg.payload = "*,*," + outsideColor + ",2-5,2-5," + middleColor;
return msg;
```

**4 Concentric Squares with Random Colors**
``` javascript 
var c1 = Math.floor(Math.random() * 255);
var c2 = Math.floor(Math.random() * 255);
var c3 = Math.floor(Math.random() * 255);

var color1 = c1 + "," + c2 + "," + c3;
var color2 = c3 + "," + c1 + "," + c2;
var color3 = c2 + "," + c1 + "," + c3;
var color4 = c3 + "," + c2 + "," + c3;
msg.payload = "*,*," + color1 + ",1-6,1-6," + color2 + ",2-5,2-5," + color3 + ",3-4,3-4," + color4;
return msg;
```

**4 Concentric Circles with Random Colors**
``` javascript 
var c1 = Math.floor(Math.random() * 255);
var c2 = Math.floor(Math.random() * 255);
var c3 = Math.floor(Math.random() * 255);

var color1 = c1 + "," + c2 + "," + c3;
var color2 = c3 + "," + c1 + "," + c2;
var color3 = c2 + "," + c1 + "," + c3;
var color4 = c3 + "," + c2 + "," + c3;

msg.payload = "2-5,0," + color1 + ",1,1," + color1 + ",6,1," + color1 + ",7,2-5," + color1 + ",0,2-5," + color1 + ",6,6," + color1 + ",1,6," + color1 + ",2-5,7," + color1;
msg.payload += ",2-5,1," + color2 + ",1,2-5," + color2 + ",6,2-5," + color2 + ",2-5,6," + color2;
msg.payload += ",2-5,2-5," + color3;
msg.payload += ",3-4,3-4," + color4;

return msg;
```

**Heart**
``` javascript 
var pink = "255,105,180";
var white = "0,0,0"

msg.payload = "0,3-4," + pink + ",1,2-5," + pink + ",2,1-6," + pink + ",3-6,0-7," + pink + ",5-6,3-4," + white + ",6,2-5," + white;
return msg;
```

**Circle**
``` javascript 
msg.payload = "2-5,*,yellow,1-6,1-6,yellow,0-7,2-5,yellow";
return msg;
```

**Smiley Face**
``` javascript 
// Yellow circle
msg.payload = "2-5,*,yellow,1-6,1-6,yellow,0-7,2-5,yellow";

// Face features
msg.payload += ",5,2,blue,5,5,blue"; // eyes
msg.payload += ",3,1,blue,2,2,blue,1,3,blue,1,4,blue,2,5,blue,3,6,blue"; // mouth
return msg;
```

**IBM Letters (need to display each letter separately)**
``` javascript 
var i = "*,7,blue,*,0,blue,3-4,*,blue";
msg.payload = i;
return msg;
```

``` javascript 
var b = "7,*,blue,0,*,blue,*,7,blue,*,0,blue,*,4,blue";
msg.payload = b;
return msg;
```

``` javascript 
var m = "0,*,blue,7,*,blue,1,6,blue,6,6,blue,2,5,blue,5,5,blue,3,4,blue,4,4,blue";
msg.payload = m;
return msg;
```

**Outline of a circle**
``` javascript 
msg.payload = "2-5,0,white,1,1,white,6,1,white,7,2-5,white,0,2-5,white,6,6,white,1,6,white,2-5,7,white";
return msg;
```

**Peace sign**
``` javascript 
msg.payload = "2-5,0,white,1,1,white,6,1,white,7,2-5,white,0,2-5,white,6,6,white,1,6,white,2-5,7,white";
msg.payload += ",3-4,*,white,2,2,white,5,2,white";
return msg;
```

**Tree**
``` javascript 
msg.payload = "2-5,7,green,1-6,3-6,green,2-5,2,green"; // green body
msg.payload += ",3-4,0-1,139,69,19"; // brown trunk
return msg;
```

### More with Sense Hats

Here is a good follow-up game that you can create easily on your Raspberry Pi's Sense Hat:
https://developer.ibm.com/recipes/tutorials/connecting-a-sense-hat-to-watson-iot-using-node-red/


