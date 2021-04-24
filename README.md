# Save-files-to-Dropbox
This Oracle APEX Plugin allows users to save and upload files directly to Dropbox

PRE-REQUISITES

Ensure you have configured REST APIs for Dropbox account to retrieve access token for use in the Plugin. 
Follow steps here - https://www.robot-hub.com/how-to-get-your-dropbox-api-access-token/#:~:text=%20How%20to%20Get%20Your%20Dropbox%20API%20Access,2%20STEP%202.%20Generate%20access%20token%20More%20

Please make sure you enable sharing (permissions) in the Individual scopes section while registering your Dropbox app.
If you intend to have the document embedded (as displayed in my sample app) ensure you enter the domain of your apex application in (Chooser / Saver / Embedder domains).

PLUGIN INSTALLATION

Import process type plugin (process_type_plugin_prc_kadeyemiapex_savetodropbox.sql) into your application and include as part of your submit page process

PLUGIN USE

On an APEX Application page: 

1. Create a File Browse page item on APEX app page and choose TABLE APEX_APPLICATION_TEMP_FILES for storage type.
2. Create a text/textarea page item on APEX app page to display generated links after successful file uploads.
3. Create page process of type plugin and select "Save files to Dropbox" Plugin.
4. Ensure the following settings information are entered:
   (a) Access Token (Mandatory) : available from Dropbox rest api configuration.
   (b) File Path (Mandatory) : to ensure files are properly organized in folder(s) e.g /home/docs.
   (c) Requested Visibility: select from available list, default role - public
   (d) Audience : select from available list, default type - public
   (e) Access : select from available list, default type - viewer
   (f) File Browse Item (Mandatory): Item created in step 1
   (g) Generate file links display item name (Optional): Item created i step 2


SAMPLE APPLICATION

Install sample application fsavetodropboxka.sql to see plugin in action
