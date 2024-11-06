1. Resource Group
Resource Group Name: cms

2. SQL Database
DB name: cms
Server: cms123.database.windows.net
DB region: us-central
Admin login: cmsadmin
Admin password: CMS4dmin
Resource group: cms
DB workload env: Development
DB compute + storage: DTU - Basic
Press the "Next: Networking" button, then select "Public Endpoint", and set both of the Firewall rules that appear to "Yes".
Set everything else to default
Run SQL queries in sql_scripts/ directory after completion, starting from the users table. Don't forget to take screenshots.

3. Storage Account
Resource group: cms
Storage account name: images1106
Advanced - Allow enabling anonymous access on individual containers: Enable
Advanced - Access tier: Cool
Network access: Enable public access from all networks (the default)
Create container named "images". Set its access level to Container.
From Security + networking > Access keys:
Blob Storage key: sbf73gPP5PzwJbNihe1/QdaF9PchaC/bK3rlJD/9//q0D7o6QX/IG4TTPHx14IGMYXm611IygM4W+AStNWjukQ==

4. Microsoft Entra ID

4.1. App Registration
Name: cmsEntraID
Who can use? "Accounts in any organizational directory (Any Microsoft Entra ID tenant - Multitenant) and personal Microsoft accounts (e.g. Skype, Xbox)"

4.2. Secret Creation
Secret description: cmsSecret
Secret Key: 71c3cef4-2887-40ff-8251-3245f912cbab
Client Secret: TyO8Q~0sJcIbFA9LpCu~fcXllsgJ6m-a5GbScc4j
Application (client) ID: d3868a33-ba64-4a4d-933d-a316a305b11c


5. Application

5.2. OPTION 2: Web App (easier)
Name: udacitycms123.azurewebsites.net
Runtime stack: Python 3.10
Pricing Plan: Free F1
If you are getting a "Validation failed for a resource" error, pick a different region.

After creation:

Settings -> Environment variables 
BLOB_ACCOUNT: images1106
BLOB_CONTAINER: images
BLOB_STORAGE_KEY: sbf73gPP5PzwJbNihe1/QdaF9PchaC/bK3rlJD/9//q0D7o6QX/IG4TTPHx14IGMYXm611IygM4W+AStNWjukQ==
SQL_SERVER: cms123.database.windows.net
SQL_DATABASE: cms
SQL_USER_NAME: cmsadmin
SQL_PASSWORD: CMS4dmin
CLIENT_SECRET: TyO8Q~0sJcIbFA9LpCu~fcXllsgJ6m-a5GbScc4j
SECRET_KEY: 71c3cef4-2887-40ff-8251-3245f912cbab
CLIENT_ID: d3868a33-ba64-4a4d-933d-a316a305b11c
Deployment Center
Source: GitHub
Pick the repo that contains the starter files.
6. Setting up OAuth2
At this point, your application should already be running. You should already be able to log in with username admin and password pass and you can create new posts or update existing ones.

The next part is getting the OAuth2 login to work.

Go to Microsoft Entra ID > App Registrations, click on the App Registration created earlier, and then pick Authentication from the left sidebar.

6.1. Microsoft Entra ID - Authentication - Add a Platform - Web
Redirect URIs: https://[IP ADDRESS FROM VM or WEB APP ADDRESS]/getAToken
logout URL: https://[IP ADDRESS FROM VM or WEB APP ADDRESS]/login

