# React Drive CMS
Publish articles directly from Google Drive to your blog with React JS. Simple setup with no transpiling.

Live demo here: 
https://ryndamere.github.io/React-drive-Test/

### Features:
- A dynamic site, but no backend to manage, no database, no server, no hosting & no maintenance
- A MS Word-like and MS Excel-like interface that users are familiar with
- Disqus comments system integration
- SendGrid email forwarding integration so that you can receive messages from the contact form on your email address.
- Regular URLs (no hashbang)
- A simple blog starter kit that can be easily customized to your liking.

### How to use:

1) In your Google Drive, create folders and files following the names and structure used here : 
https://drive.google.com/drive/folders/1r9HkrXDkPoq9hdVa3cBscvWHlsNC8D-7

2) Add to the "Dashboard" sheet the following bound script:
https://gist.github.com/misterfresh/e1c9cf0bb4c777221f84   . 
This will create a new "Update" button with which you can automatically update the Dashboard file. Change the projectFolderName on line 9 in the Dashboard Script to the name of your drive folder if necessary. Publish the Dashboard sheet to the web via File>Publish to the Web.

3) In order for the contact form to work, publish the following script as a Google Web App:
https://gist.github.com/misterfresh/b69d29a97cf415980be2  . In your "Visitors" Google spreadsheet, go to Tools>Script Editor. You can create a free SendGrid account and paste your SendGrid API key in the script. Save the script and click on Publish>Deploy as Web App. .

4) Fill in the correct values in ./conf.js :
    - "dashboardId" is the id of the "Dashboard" Google spreadsheet.
    - "sendContactMessageUrlId" is the id of the Google Web App script that does the email forwarding
    - "shortname" is the website's Disqus identifier
    - "root" is an optional url parameter, that would be the name of the project on GitHub pages.

5) Push to a "gh-pages" branch on GitHub to publish on GitHub Pages

That's it!

### How to customize, no tools required:
1. [Add the repo folder as Sources overrides in Chrome DevTools( how to ) ](https://medium.com/@jmatix/using-chrome-as-a-local-web-server-af04baffd581)
2. Open page "[chrome://net-internals/#hsts](chrome://net-internals/#hsts)" in Chrome and add "drivecms.local" as HSTS domain
3. You should now be able to open [http://drivecms.local/](http://drivecms.local/) in Chrome
4. Edit source code in "drivecms.local" folder
5. No need to build or compile, just refresh the [http://drivecms.local/](http://drivecms.local/) page to view changes

