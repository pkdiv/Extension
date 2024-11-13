# LinkedIn Connect Extension

LinkedIn connect is a extension that automates sending connect requests to people. 

## Installation Instruction

1. Navigate to chrome://extensions in Google Chrome
2. Enable Developer Mode if not enabled using the toggle switch
3. Click on **Load Unpacked** 
4. Navigate to the directory where the extension is downloaded and select the directory
5. The extension will be added and can be access by clicking on the puzzle icon present on the seachbar

## Architecture

- popup.html and popup.js allow the user to start the automation process of connecting. 
	- popup.js sends a message to the background service when a click is detected
- background service worker listens to the message sent by the popup.js file and forwards the start / stop request to the content script file
- content script listens to the message sent by the background file to start or stop the automation
- content script also send a message back to the background service worker to update the count of number of buttons clicked
