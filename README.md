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



