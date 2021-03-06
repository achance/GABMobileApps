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


## Configure Authentication 

Once the demo mobile app is setup and running, we can add authentication. For this demo, we will setup Google Authentication, but you could use any available compatible provider. 

To configure Google authentication, you must register your application with Google. To do this, you will need a Google account. If you don't already have one, or don't want to use your personal account, you will need to create an account. This account must have a valid email address. 

1. From the **Azure Portal**, navigate to your mobile app. From the **Overview** tab, locate and copy the **URL** for your application. This is needed to register with Google. The **URL** should be in the format: `https://myappname.azurewebsites.net`

2. Navigate to the **[Google APIs Console](https://console.developers.google.com)**, sign into the Google account you want to use when prompted. 

3. To register your application, you need to create a project to associate with your Azure app. From the main dashboard, click on **Create Project** 

![Google API Project][GoogleAPICP]

[GoogleAPICP]: https://github.com/achance/GABMobileApps/blob/master/Screenshots/GoogleAPICP.PNG?raw=true "Google API Project"

Name your project and then click on **Create**. Wait a few moments for the creation to complete, and then you should be back at the main dashboard.

4. Click on **Library** from the menu on the left. We want to enable the **Google+ API**. You can use the search box, or click on the **Social** category, and choose it from there. 
After you select the appropriate API, click on **Enable**

![Google API Google+][GoogleAPIGPlus]

[GoogleAPIGPlus]: https://github.com/achance/GABMobileApps/blob/master/Screenshots/GoogleAPIGPlus.PNG?raw=true "Google API Credentials"

5. Now we need to configure the **Credentials** for the app. Click on the **Credentials** icon on the left, and then click on the **OAuth Consent Screen** tab. Choose an **Email address**, enter a **Product name**, and then click on **Save**.

![Google API Credentials][GoogleAPICred]

[GoogleAPICred]: https://github.com/achance/GABMobileApps/blob/master/Screenshots/GoogleAPICred.PNG?raw=true "Google API Credentials"

Back on the **Credentials** tab, click **Create Credentials**, **OAuth Client ID**, and then select **Web application**. 

![Google API Credentials][GoogleAPICred1]

[GoogleAPICred1]: https://github.com/achance/GABMobileApps/blob/master/Screenshots/GoogleAPICred1.PNG?raw=true

Enter a name for your **OAuth Client ID**. Under **Restrictions**, enter the URL for your app into **Authorized Javascript origins**. This should be the URL you copied from the Azure portal in step 1. 
For the **Authorized Redirect URI**, append your URL with the following: **_/.auth/login/google/callback_**. 

For example, `https://myappname.azurewebsites.net/.auth/login/google/callback`
 
Ensure that both URLs begin with **https://**. Once you have added the URLs, click on **Create**. 

7. Now, you should see a screen with your **OAuth Client ID** and **Client Secret**. Copy these for reference in a later step. 

8. Now we need to make the changes in Azure to finish setting up the Google Authentication. Navigate back to the **Azure Portal**, and click on your application. Under **Settings**, click on **Authentication/Authorization**.

![Azure App Settings][AppSettingsAuth]

[AppSettingsAuth]: https://github.com/achance/GABMobileApps/blob/master/Screenshots/AppSettingsAuth.PNG?raw=true "Azure App Authentication" 

3. Toggle **App Service Authentication** to **ON**. Then select **Google** under **Authentication Providers**. Paste in your **Client ID** and **Client Secret** from Google and then click **OK**. 

4. Now we have enabled Google Authentication, but our settings will still allow any user to access the app. Azure App Service defaults to anonymous access. 
To fix this, change the **Action to take when request is not authenticated** to **Log in with Google**, and then click **Save**. 
This setting forces the app to require all requests to be authenticated. If any request isn't already authenticated, then it will redirect to Google for the authentication. 

![Azure App Settings][AppSettingsAuth2]

[AppSettingsAuth2]: https://github.com/achance/GABMobileApps/blob/master/Screenshots/AppSettingsAuth2.PNG?raw=true "Azure App Authentication"

Note, we have still only configured **Authentication**. Users will be authenticated to the app, but any addtional **Authorization** would need to be setup if we wanted to control or restrict access. 

We can test our configuration now by simply navigating to the app URL in a web browser. If everything is configured correctly, then you should see the redirect for the Google authentication. 

## Configure backend to restrict permissions

Azure app service also defaults anonymous access for the backend APIs. Since we have authentication configured, we want to restrict access for authenticated clients only. 

There are a few ways that we can set this up, but for the purpose of the demo, we are going to use the Azure portal. This option is only available for the **Node.js** backend, which should be configured already. 

1. From the **Azure portal**, navigate back to your app, and then under **Mobile**, select **Easy Tables**.  

![Easy Tables][EasyTables]

[EasyTables]: https://github.com/achance/GABMobileApps/blob/master/Screenshots/EasyTables.PNG?raw=true "Easy Tables"

2. Select the **todoitem** table that should have been created earlier. Click **Change Permissions** and then change all of the permissions to **Authenticated access only** and **Save**. 

3. Now, we should have restricted anonymous access to our app's backend. We can test this is working in **Visual Studio**. Open the project that you downloaded earlier. Run the app in the browser emulator, and you should see the error for **Unexpected connection failure**. 

![Connection failure][ConnFail]

[ConnFail]: https://github.com/achance/GABMobileApps/blob/master/Screenshots/ConnFail.PNG?raw=true "Connection failure"






