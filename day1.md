## Todo 
- Research what kind of technolgies are being used
- Identify a tech stack to build and stick with it
- Project folder set up
-
I feel like it makes sense to research what a broswer extension really is and how they work
Im gonna use this md as a space for mental notes, wiritng things and thoughts down as they coe
like a little diary if you will

a browser extenion can be thought of as a small app that can:
- watch what happens as you browse
- intercept and modify web requests
- store data locally
- show ui elemetns



## The core files
i think this will be important for some reason

## manifest.json
- Can be thought of as the extensons birth certificate and a config file that ties it all together
It tells the browser numerous things like:
- What the extension is called
- What permissions it needs (like acsess to tabs, web requests, storage etc)
- Whcih files to load and when 
- What version of the extension api we are using

# Background script ( background.js or service_worker.js)
- This runs in the background constantly 
- It listens to browser events like tabs opened , web pages loaded , reqeusts made etc
- It can intercept and blocl/modify  network requests before they happen
- Coordinates between different parts of the extension
- Stores data
For this project this is where wed block tracking requests before they reach the trackers server

## Content Script(content.js) - The page inspector
This is going to get injected into the web pages the user visits it can read and modify the pages DOM
- Reads everything on the page
- Can modify the page (hide elemts, change text, inject warnings)
- Can communicate with the background script
For the project this is where we can scan forms for suspicious data collection or delete tracking
scripts emebeded into the page

## Popup (popup.html + popup.js) - The User Interface
- This is the little window that appears when someone clicks your extension icon in the toolbar.
What it does:

- Shows info to the user (like "47 trackers blocked")
- Lets users adjust settings
- Displays your extension's dashboard
For your privacy extension: This is where you'd show users what data was about to be collected.


## Options Page (options.html) - Optional Settings Panel
A separate page for more detailed settings (like a full preferences screen).
