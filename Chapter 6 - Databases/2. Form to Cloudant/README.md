# Form to Cloudant

This module will demonstrate how to create a form in Node Red, using the dashboard palette, and send the form's information to a Cloudant database.

### ![Link to Video](https://youtu.be/-kJmUZFIRMg)

Video length: 4:11 minutes

### Nodes Needed
- 1 form node (from the dashboard palette)
- 1 debug 
- 1 Cloudant receiving node

### Instructions

If you have download the dashboard palette, skip to step 3.

1. Click the three bar menu in the top right corner and select manage palette. 

<img src="https://github.ibm.com/L-Gamerman/NodeRedEducation/blob/master/Chapter%201%20-%20Getting%20Started/Screenshots/manage.png" height="500">

2. Click on the install tab and type in node-red-dashboard. 

<img src="https://github.ibm.com/L-Gamerman/NodeRedEducation/blob/master/Chapter%201%20-%20Getting%20Started/Screenshots/install_tab.png" height="500">

<img src="https://github.ibm.com/L-Gamerman/NodeRedEducation/blob/master/Chapter%201%20-%20Getting%20Started/Screenshots/node-red-dashboard-install.png" height="500">

3. Pull out a form node on the workspace and double click to edit. 

<img src="https://github.ibm.com/L-Gamerman/NodeRedEducation/blob/master/Chapter%201%20-%20Getting%20Started/Screenshots/form1.png" height="500">

  - Group: Add new ui_group, click the pen symbol to the right. 
   - Name the group whatever you like
    
 <img src="https://github.ibm.com/L-Gamerman/NodeRedEducation/blob/master/Chapter%201%20-%20Getting%20Started/Screenshots/form2.png">
 
  - Tab: Add new ui_tab, click the pen symbol to the right. 
  - Name the tab whatever you like
  
  <img src="https://github.ibm.com/L-Gamerman/NodeRedEducation/blob/master/Chapter%201%20-%20Getting%20Started/Screenshots/form3.png">
  
  - Click add twice. 
  - In form elements, type in whatever elements you want on your form. 
  - Label is what is displayed on the form itself.
  - Name is how you would reference that element programmically. E.g. msg.payload.name
  
  <img src="https://github.ibm.com/L-Gamerman/NodeRedEducation/blob/master/Chapter%201%20-%20Getting%20Started/Screenshots/form4.png">

4. Attach the form node to a Cloudant receiving node and a debug node. 

<img src="https://github.ibm.com/L-Gamerman/NodeRedEducation/blob/master/Chapter%201%20-%20Getting%20Started/Screenshots/cloudant_flow.png" >

5. Edit the Cloudant node. 

  - Service: External cloudant or couchdb service
  
  <img src="https://github.ibm.com/L-Gamerman/NodeRedEducation/blob/master/Chapter%201%20-%20Getting%20Started/Screenshots/cloudant_edit.png" height="500">
  
  - Server: Add new cloudant..., click the pen symbol to the right. 
  - Enter the host, username and password from your Cloudant credentials (listed in the Service Credentials tab on your Cloudant on Bluemix)
  
    <img src="https://github.ibm.com/L-Gamerman/NodeRedEducation/blob/master/Chapter%201%20-%20Getting%20Started/Screenshots/cloudant_edit2.png" height="500">
    
  - Click add. 
  - Database: The name of the database that you want to write to. 
  - Operation: insert

6. Click deploy.

7. To open the dashboard user interface, copy the your Node Red instance URL, including mybluemix.net, and after the slash, type "ui."

  - Ex. https://xxx-xxx.mybluemix.net/ui

  <img src="https://github.ibm.com/L-Gamerman/NodeRedEducation/blob/master/Chapter%201%20-%20Getting%20Started/Screenshots/form.png">
  
8. Fill out your form and click submit. 

9. Open Cloudant. To do this, go to your services dashboard on Bluemix and click on Cloudant. On the Cloudant landing page, click launch. 

10. Click the 3 disks on the menu bar to the left.

  <img src="https://github.ibm.com/L-Gamerman/NodeRedEducation/blob/master/Chapter%201%20-%20Getting%20Started/Screenshots/db_menu.png">
  

11. Click on your database. 

  <img src="https://github.ibm.com/L-Gamerman/NodeRedEducation/blob/master/Chapter%201%20-%20Getting%20Started/Screenshots/all_dbs.png">

12. To check the document's payload, click on the pen symbol to the right of the document box. 

  <img src="https://github.ibm.com/L-Gamerman/NodeRedEducation/blob/master/Chapter%201%20-%20Getting%20Started/Screenshots/db_doc.png">
  
#### Result:

Your form entries are stored in the payload of the document and printed in the Node Red debug console. 

<img src="https://github.ibm.com/L-Gamerman/NodeRedEducation/blob/master/Chapter%201%20-%20Getting%20Started/Screenshots/doc_payload.png">

<img src="https://github.ibm.com/L-Gamerman/NodeRedEducation/blob/master/Chapter%201%20-%20Getting%20Started/Screenshots/form_debug.png">
