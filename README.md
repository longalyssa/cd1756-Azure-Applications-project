1. Resource Group
Resource Group Name: cms

2. SQL Database
DB name: cms
Server: cms.database.windows.net
DB region: us-east
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
Storage account name: images114 (needs to be unique)
Advanced - Allow enabling anonymous access on individual containers: Enable
Advanced - Access tier: Cool
Network access: Enable public access from all networks (the default)
Create container named "images". Set its access level to Container.
From Security + networking > Access keys:
Blob Storage key: wv2ld/u2ANQGF4NRE/XUj/jmCodCm7OE3+vvLMQdu3GbN1rx36/REk59LYmwzqv74XICRMOR6vUb+AStDI8GrA==

4. Microsoft Entra ID

4.1. App Registration
Name: cmsEntraID
Who can use? "Accounts in any organizational directory (Any Microsoft Entra ID tenant - Multitenant) and personal Microsoft accounts (e.g. Skype, Xbox)"

4.2. Secret Creation
Secret description: cmsSecret
Secret Key: 6956e52a-9b20-4baf-b6e2-fd4f082af6af
Client Secret: I_h8Q~Bf6X8AARUgineqv~N5riQbcazSFKGnAcRY
Application (client) ID: 7fe7dce5-c3f9-4ee3-942e-4893c3609580


5. Application

5.2. OPTION 2: Web App (easier)
Name: udacitycms.azurewebsites.net
Runtime stack: Python 3.10
Pricing Plan: Free F1
If you are getting a "Validation failed for a resource" error, pick a different region.

After creation:

Settings -> Environment variables 
BLOB_ACCOUNT: images114
BLOB_CONTAINER: images
BLOB_STORAGE_KEY: wv2ld/u2ANQGF4NRE/XUj/jmCodCm7OE3+vvLMQdu3GbN1rx36/REk59LYmwzqv74XICRMOR6vUb+AStDI8GrA==
SQL_SERVER: cms.database.windows.net
SQL_DATABASE: cms
SQL_USER_NAME: cmsadmin
SQL_PASSWORD: CMS4dmin
CLIENT_SECRET: I_h8Q~Bf6X8AARUgineqv~N5riQbcazSFKGnAcRY
SECRET_KEY: 6956e52a-9b20-4baf-b6e2-fd4f082af6af
CLIENT_ID: 7fe7dce5-c3f9-4ee3-942e-4893c3609580
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

