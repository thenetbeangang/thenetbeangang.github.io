FileVista v8.9.16.0
Web File Manager (Self-Hosted File Sharing, Own Cloud Storage)
Copyright C 2006-2023 GleamTech
https://www.gleamtech.com/filevista

FileVista is a Web File Manager (Self-Hosted File Sharing, Own Cloud Storage).
FileVista turns your web site into a web file server in few minutes and lets you share files with your clients or staff using any browser or device.

---------------------------------------------------
Information on package contents:
---------------------------------------------------

  Web Deploy package can be used either for 

  - Automated installation on a dedicated server with IIS 7.0 (minimum) and IIS extension Web Deploy

  - or Manual installation on a shared hosting

---------------------------------------------------
Automated installation via Web Deploy:
---------------------------------------------------

  1. Download and install Microsoft's Web Deploy extension for IIS if it's not already installed:
     http://www.iis.net/download/webdeploy

  2. Open IIS Manager and select and right-click on a web site that you will install FileVista to and 
     select Deploy -> Import Application from the context menu.     

  3. Import Application Package wizard will be displayed. Browse FileVista-vX.X.X.X-WebDeploy.zip that you have downloaded 
     and complete the wizard. Configurations like creating an IIS application and setting permissions will be done automatically.

---------------------------------------------------
Manual installation on a shared hosting:
---------------------------------------------------

  1. Extract the "FileVista" subfolder from the zip package.

  2. Copy this subfolder to the target web server (e.g. via FTP).

  3. Create an IIS Application for this folder in IIS manager (if you have access to) or in your hosting control panel. 
     If you don't have this option, request your hosting company/server administrator to do this for you.
     Please make sure you choose an ASP.NET 4.0 application pool (integrated mode) for FileVista.

---------------------------------------------------
Configuration:
---------------------------------------------------

  After the installation is complete, you can run the application via navigating to your server's URL + installed FileVista folder name 
  (e.g. http://localhost/FileVista or http://www.MyWebSite.com/FileVista) in your browser. You will be greeted by the Configuration Wizard 
  (configuration.aspx). This wizard will help you configure the application for first run by guiding you through the steps like choosing
  a database type and setting administrator name and password. The wizard will also show you information on possible problems such as 
  lack of permissions and it will suggest instructions to solve them. After you finish the wizard successfully, you will be able to 
  log into the application with the administrator credentials. If you cannot even start the Configuration Wizard then there is 
  a problem with your installation such as wrong ASP.NET version. Please make sure that ASP.NET 4.0 is installed and it's the active 
  version for the installed FileVista folder.

---------------------------------------------------
Overriding resource files:
---------------------------------------------------

  "FileVista\App_GlobalResources\OriginalFiles" folder contains the copies of resource files such as 
  the language files which are already embedded into GleamTech.FileVista.dll. For example, you can 
  use these files to create a new translation or modify an existing translation. You should copy the
  modified files to the corresponding place under "FileVista\App_GlobalResources" to override an embedded
  resource. Please only copy the required files and not the whole folder as future updates to 
  GleamTech.FileVista.dll may include   newer versions of those files which may be necessary to run 
  the latest version properly.
 
  New or modified files under "FileVista\App_GlobalResources" folder should trigger restarting of the ASP.NET 
  application. So, FileVista should automatically recognize the changes to the resource files under this 
  folder. If FileVista does not recognize the changes then you can touch (simply open & save) 
  "FileVista\Web.config" file to force FileVista to see the changes.
 
---------------------------------------------------
Translating to a new language:
---------------------------------------------------

  Please first see "Overriding resource files" above for information on where to find original language files.

  To override an existing embedded language or to add a newly translated language, put the modified 
  language files or the newly translated language files in "FileVista\App_GlobalResources\Languages" 
  subfolder. Note that there are 2 separate files "FileUltimate-xx.xml" and "FileVista-xx.xml" for 
  a single language, one for FileVista and one for FileUltimate which FileVista is built on top of. 
  Both of these files should be translated and copied as FileVista uses translations from both files.
 
  Language files are simple XML files. To create a new language file, make copies of "FileUltimate-en.xml"
  and "FileVista-en.xml" and rename them to a standard language name (refer to Culture Name column in 
  this table: https://msdn.microsoft.com/en-us/goglobal/bb896001.aspx). For instance, rename them to 
  "FileUltimate-de.xml" and "FileVista-de.xml" for German language. Edit the new xml files and translate 
  each string element but do not modify the key attributes. If a string includes a place holder {0},
  do not forget to include it in the translated string too. You can create language files also for 
  specific cultures. For instance, you can create "FileUltimate-de-CH.xml" and "FileVista-de-CH.xml"
  for German in Switzerland. There is a fallback mechanism, FileVista will first look for the language
  file "FileVista-de-CH.xml" and if the file is not found, it will load the general language file of that 
  culture which is "FileVista-de.xml".

  We will appreciate if you send us the language files you created so that we can bundle them in 
  future versions.
  
Support Portal:
https://support.gleamtech.com/
  