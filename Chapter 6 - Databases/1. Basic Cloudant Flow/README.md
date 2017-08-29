# Basic Cloudant Flow

This module will show how to send a payload from Node Red and store it in a Cloudant database.

### ![Link to Video](https://youtu.be/Cds3ziauml4)

Video length: 3:04 minutes

### Nodes Needed:
- 1 inject
- 1 debug
- 1 receiving Cloudant node

### Instructions

1. Go to your Bluemix dashboard and click "Create Service". 

![](https://github.ibm.com/L-Gamerman/STSA-Weather-Demo/blob/master/README_screenshots/create_service.png)

2. In the search box, type in "Cloudant". 

3. Click on "Cloudant NoSQL DB" application under services. Choose the first version.

![](https://github.ibm.com/L-Gamerman/STSA-Weather-Demo/blob/master/README_screenshots/service_cloudant.png)

4. Click the blue "Create" button on the bottom right side of the screen. 

![](https://github.ibm.com/L-Gamerman/STSA-Weather-Demo/blob/master/README_screenshots/create_service2.png)

5. On your Bluemix dashboard, click on the Cloudant service. 

There are two possibilities to connect Node Red with another service. 

Option 1:

- On the left panel, click "Service credentials". 

![](https://github.ibm.com/L-Gamerman/STSA-Weather-Demo/blob/master/README_screenshots/service_cred.png)

- Click "New credential". 

<img src="../Chapter%201%20-%20Getting%20Started/Screenshots/new_cred.png">

- Click add. 

<img src="../Chapter%201%20-%20Getting%20Started/Screenshots/new_cloud_cred.png">

- Click "View credentials". 

![](https://github.ibm.com/L-Gamerman/STSA-Weather-Demo/blob/master/README_screenshots/view_credentials.png)

- In the Node Red Cloudant node, copy and paste the username and password from your Bluemix credentials to the corresponding text boxes in the node. 

![](../Chapter%201%20-%20Getting%20Started/Screenshots/creds.png)

Option 2: 

- On the left panel, click "Connections".

![](https://github.ibm.com/L-Gamerman/STSA-Weather-Demo/blob/master/README_screenshots/connections.png)

- Click the blue "Create Connection" button. 

![](https://github.ibm.com/L-Gamerman/STSA-Weather-Demo/blob/master/README_screenshots/create_connection.png)

- Select your Node Red Application and click connect.

![](https://github.ibm.com/L-Gamerman/STSA-Weather-Demo/blob/master/README_screenshots/select_app.png)

- Click connect. 

6. Back in Node Red, pull out an inject node and a Cloudant receiving node (a node with the point on the left side) to the workspace.

![](https://github.ibm.com/L-Gamerman/STSA-Weather-Demo/blob/master/README_screenshots/test_name.png)  |  ![](https://github.ibm.com/L-Gamerman/STSA-Weather-Demo/blob/master/README_screenshots/cloudant.png)

2. Double click the inject node to edit its properities. Change the payload type to string and write "test" and your name. 

<img src="https://github.ibm.com/L-Gamerman/STSA-Weather-Demo/blob/master/README_screenshots/test_edit.png" width="450" height="400" />

3. Wire the inject to the Cloudant node. 

![](https://github.ibm.com/L-Gamerman/STSA-Weather-Demo/blob/master/README_screenshots/flow.png)

4. Double click the Cloudant node. 
  - Service: External cloudant or couchdb service
  - Server: Add new Cloudant, click the pen icon to the right to configure. 
  
<img src="https://github.ibm.com/L-Gamerman/STSA-Weather-Demo/blob/master/README_screenshots/edit_cloud.png" width="500" height="400">

  - Enter the host, username and password from your Cloudant credentials. 

<img src="../Chapter%201%20-%20Getting%20Started/Screenshots/cloudant_edit2.png" width="500" height="400">

  - Database: The name of your Cloudant database
  - Operation: insert
  - Click done
  
5. On the workspace screen, click Deploy in the top right corner. 

![](https://github.ibm.com/L-Gamerman/STSA-Weather-Demo/blob/master/README_screenshots/deploy.png)

6. Inject the data by clicking the blue button to the left of the inject node. 

![](https://github.ibm.com/L-Gamerman/STSA-Weather-Demo/blob/master/README_screenshots/blue.png)

7. Open Cloudant. To do this, go to your services dashboard on Bluemix and click on Cloudant. On the Cloudant landing page, click launch. 

8. Click the 3 disks on the menu bar to the left.

  <img src="../Chapter%201%20-%20Getting%20Started/Screenshots/db_menu.png">
  

9. Click on your database. 

  <img src="../Chapter%201%20-%20Getting%20Started/Screenshots/nr_db.png">

10. To check the document's payload, click on the pen symbol to the right of the document box. 

  <img src="../Chapter%201%20-%20Getting%20Started/Screenshots/db_doc2.png">

#### Result:

Now you have a flow that connects to a Cloudant database. 

![](../Chapter%201%20-%20Getting%20Started/Screenshots/db_doc_result.png)

### [Next module: Form to Cloudant >>](../Chapter%206%20-%20Databases/2.%20Form%20to%20Cloudant)

