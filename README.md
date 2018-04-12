# GABMobileApps
Mobile Apps Demo for Azure Boot Camp 2018

## Create a new resource using the Mobile Apps Quickstart 

1. If you haven't already, sign into the [Azure Portal](https://portal.azure.com).
2. Click on **Create a new resource**. 

![Create a resource image][CreateAResource]

[CreateAResource]: https://github.com/achance/GABMobileApps/blob/master/Screenshots/CreateAResource.PNG?raw=true "Create A Resource"

3. Search for **Mobile Apps Quickstart**.

![MAQ Image 1][MAQ1]

[MAQ1]: https://github.com/achance/GABMobileApps/blob/master/Screenshots/MAQ.PNG?raw=true "Search for Mobile Apps"

4. Select the appropriate resource.
5. Click on **Create**.

![MAQ Image 2][MAQCreate]

[MAQCreate]: https://github.com/achance/GABMobileApps/blob/master/Screenshots/MAQCreate.PNG?raw=true "Create Quickstart App"

6. Give your app a name.
7. By default, it should create a new resource group with the same name as your app. 
   * You could use an existing resource group, or name your resource group differently.

![MAQ Create 2][MAQCreate2]

[MAQCreate2]: https://github.com/achance/GABMobileApps/blob/master/Screenshots/MAQCreate2.PNG?raw=true "Create Quickstart App options"

8. Click on **Create**. You should see a notification that your app is being deployed.

![MAQ Deploy][MAQDeploy]

[MAQDeploy]: https://github.com/achance/GABMobileApps/blob/master/Screenshots/MAQDeploy.PNG?raw=true "Deploy App"

## Configure the server project ##

1. From the main dashboard, select your newly created App Service for your mobile app
   * If you don't see this on your dashboard, click the **App Services** icon from the menu
   and then choose your App Service. 
   
![Dashboard][Dashboard]

[Dashboard]: https://github.com/achance/GABMobileApps/blob/master/Screenshots/Dashboard.PNG?raw=true "Dashboard"

![App Services][AppServices]

[AppServices]: https://github.com/achance/GABMobileApps/blob/master/Screenshots/AppServices.PNG?raw=true "App Services"

2. Under **Deployment**, choose the **Quickstart** option. Select your platform (for this example, we will be using the **Cordova** platform).

![Quickstart][Quickstart]

[Quickstart]: https://github.com/achance/GABMobileApps/blob/master/Screenshots/Quickstart.PNG?raw=true "Quickstart"

3. Create and configure the database. By default, the Quickstart app will come with SQLite enabled, but we want to create a standalone SQL Database.

![Database Connection][DB1]

[DB1]: https://github.com/achance/GABMobileApps/blob/master/Screenshots/DB1.PNG?raw=true "Database Connection"

Follow the prompts to add a new data connection. Create a new database. Fill in the required info. Create a new server.
To keep things simple, we can name our database and server similar to our app. You can keep the default settings for location and pricing tier.

![Database Connection 2][DB2]

[DB2]: https://github.com/achance/GABMobileApps/blob/master/Screenshots/DB2.PNG?raw=true "Database Connection"

If the data connection is created successfully, you should now see this under **Connect a database**:

![Data Connection Succes][DCSuccess]

[DCSuccess]: https://github.com/achance/GABMobileApps/blob/master/Screenshots/DCSuccess.PNG?raw=true "Data Connection"

4. Now we need to **Create a table API**. For the Quickstart demo, we want to select the Node.js backend. You could alternatively choose C#.

![Table API][TableAPI]

[TableAPI]: https://github.com/achance/GABMobileApps/blob/master/Screenshots/TableAPI.PNG?raw=true "Table API"

5. Click the checkbox to overwrite all site contents. Then, click on **Create TodoItem Table**. 
This will create the to-do item table in the database you selected in the previous step. This is required for the Quickstart demo app to function properly.

6. Under **Configure your client application**, ensure that **CREATE A NEW APP** is selected and then click on **Download**. 

![App Download][AppDownload]

[AppDownload]: https://github.com/achance/GABMobileApps/blob/master/Screenshots/AppDownload.PNG?raw=true "App Download"

This will download a ZIP file containing the project for the Quickstart demo. 

7. Extract the ZIP file. Locate the solution file (.sln) and open it with Visual Studio. **Visual Studio 2017** is recommeded for working with this demo.  

8. In Visual Studio, if you are prompted to upgrade the project, then do so. Select your platform from the drop-down options. For this demo, we will focus on **Android**. 
Choose the default option to run the emulator in your browser. 

![VS Debug][VSDebug]

[VSDebug]: https://github.com/achance/GABMobileApps/blob/master/Screenshots/VSDebug.PNG?raw=true "VS Debug"

9. To run your app, press **F5** or click on the green start arrow. The app should launch in the Chrome browser. Test the app's functionality by adding a new "To-do" item.

The demo app is setup to insert the data into your **TodoItem** table for the SQL database that was configured on the mobile app backend. The app will display the items (records) available in the table inside of a list.
