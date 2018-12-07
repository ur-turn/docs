

# PowerSchool REST API

In order to access the API, we'll need OAuth credentials. To accomplish this,
a UR TURN plugin will need to be created.

Download the following file and save to your desktop:

[plugin.xml](plugin.xml)

<?xml version="1.0" encoding="UTF-8"?>
<plugin xmlns="http://plugin.powerschool.pearson.com" 
xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" 
xsi:schemaLocation="http://plugin.powerschool.pearson.com plugin.xsd" 
name="UR TURN School Data Sync" 
version="1.0.0" 
description="Plugin for Powerschool REST API for UR TURN"> 
<oauth></oauth> 
<publisher name="UR TURN SBC"> 
<contact email="support@urturn.org" /> 
</publisher>  
</plugin>

2. Sign in to the PowerSchool admin portal website using your System Administrator credentials.

3. On the start page, choose System from the main menu, then go to System Settings > Plugin Management Configuration > Install.

4. Enter or select the plug-in installation file you just created (.xml), and then choose Install. The plug-in will appear in the Installed Plugins section on the Plugin Management Dashboard page. Make sure the plug-in is enabled. If it is not, choose the Enable option on the Plugin Management Dashboard page.

5. On the Plugin Management Dashboard page, make sure that the plugin is enabled.

6. Choose Data Configuration to view the OAuth credentials that were generated for the plug-in.

7. Record the values for the Client ID and Client Secret.

<small>
[adapted from Microsoft School Data Sync](https://docs.microsoft.com/en-us/schooldatasync/how-to-deploy-school-data-sync-by-using-powerschool-sync#BK_REST)
</small>
