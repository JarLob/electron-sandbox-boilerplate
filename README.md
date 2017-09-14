# electron-sandbox
A simple example of a sandboxed renderer process with the ability to communicate to the backend (main.js) through IPC.

## why?
If you're dealing with potentially untrusted content (displaying videos,images, text, etc..) in your Electron application, then you should run it with the sandbox enabled. The sandbox provided by Chrome is very strong, it has the ability to mitigate zeroday exploits within the Chrome browser engine (Blink) by restricting the ability of the attacker.

The sandbox is disabled by default. Enabling it however removes the ability to use NodeJS freely within the renderer process. These backend tasks should be moved from the renderer process to the main process. The renderer process can trigger these tasks and get return values. 

