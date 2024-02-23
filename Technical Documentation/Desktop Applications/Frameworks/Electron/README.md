### Important Points
- Entry point of electron applications is `main.js`
- Many of Electron's core modules are Node.js [event emitters](https://nodejs.org/api/events.html#events) that adhere to Node's asynchronous event-driven architecture. The app module is one of these emitters.
- `author` and `description` must be mentioned inside `package.json`
- In Electron, each window displays web contents that can be loaded from either a local HTML file or a remote URL.
- The [`app`](https://www.electronjs.org/docs/latest/api/app) module, which controls your application's event lifecycle.
- The [`BrowserWindow`](https://www.electronjs.org/docs/latest/api/browser-window) module, which creates and manages application windows.
- In Electron, browser windows can only be created after the `app` module's [`ready`](https://www.electronjs.org/docs/latest/api/app#event-ready) event is fired. You can wait for this event by using the [`app.whenReady()`](https://www.electronjs.org/docs/latest/api/app#appwhenready) API.
- Application windows behave differently on each OS, and Electron puts the responsibility on developers to implement these conventions in their app.
	- In general, you can use the `process` global's [`platform`](https://nodejs.org/api/process.html#process_process_platform) attribute to run code specifically for certain operating systems.
- **[Quit the app when all windows are closed (Windows & Linux)](https://www.electronjs.org/docs/latest/tutorial/quick-start#quit-the-app-when-all-windows-are-closed-windows--linux "Direct link to Quit the app when all windows are closed (Windows & Linux)")**
	- On Windows and Linux, exiting all windows generally quits an application entirely.
	- To implement this, listen for the `app` module's [`'window-all-closed'`](https://www.electronjs.org/docs/latest/api/app#event-window-all-closed) event, and call [`app.quit()`](https://www.electronjs.org/docs/latest/api/app#appquit) if the user is not on macOS (`darwin`).
- **[Open a window if none are open (macOS)](https://www.electronjs.org/docs/latest/tutorial/quick-start#open-a-window-if-none-are-open-macos "Direct link to Open a window if none are open (macOS)")**
	- Whereas Linux and Windows apps quit when they have no windows open, macOS apps generally continue running even without any windows open, and activating the app when no windows are available should open a new one.
	- To implement this feature, listen for the `app` module's [`activate`](https://www.electronjs.org/docs/latest/api/app#event-activate-macos) event, and call your existing `createWindow()` method if no browser windows are open.
	- Because windows cannot be created before the `ready` event, you should only listen for `activate` events after your app is initialized. Do this by attaching your event listener from within your existing `whenReady()` callback.
- Access Node.js from the renderer with a preload script
	- To print out the version numbers for Electron and its dependencies onto your web page.
		- Accessing this information is trivial to do in the main process through Node's global `process` object. However, you can't just edit the DOM from the main process because it has no access to the renderer's `document` context. They're in entirely different processes!
		- This is where attaching a **preload** script to your renderer comes in handy. A preload script runs before the renderer process is loaded, and has access to both renderer globals (e.g. `window` and `document`) and a Node.js environment.
- Preload scripts are injected before a web page loads in the renderer, similar to a Chrome extension's [content scripts](https://developer.chrome.com/docs/extensions/mv3/content_scripts/). To add features to your renderer that require privileged access, you can define [global](https://developer.mozilla.org/en-US/docs/Glossary/Global_object) objects through the [contextBridge](https://www.electronjs.org/docs/latest/api/context-bridge) API.

### Package and distribute your application[​](https://www.electronjs.org/docs/latest/tutorial/quick-start#package-and-distribute-your-application "Direct link to Package and distribute your application")
- The fastest way to distribute your newly created app is using [Electron Forge](https://www.electronforge.io/).

**CAUTION:** 
- Although you need Node.js installed locally to scaffold an Electron project, Electron **does not use your system's Node.js installation to run its code**. Instead, it comes bundled with its own Node.js runtime. This means that your end users do not need to install Node.js themselves as a prerequisite to running your app.
- If you are on a Windows machine, please do not use [Windows Subsystem for Linux](https://learn.microsoft.com/en-us/windows/wsl/about#what-is-wsl-2) (WSL) when following this tutorial as you will run into issues when trying to execute the application.
- [ECMAScript modules](https://nodejs.org/api/esm.html) (i.e. using `import` to load a module) are currently not directly supported in Electron. You can find more information about the state of ESM in Electron in [electron/electron#21457](https://github.com/electron/electron/issues/21457).
- Checking against Node's [`process.platform`](https://nodejs.org/api/process.html#process_process_platform) variable can help you to run code conditionally on certain platforms. Note that there are only three possible platforms that Electron can run in: `win32` (Windows), `linux` (Linux), and `darwin` (macOS).

**NOTE:**
- From Electron 20 onwards, preload scripts are **sandboxed** by default and no longer have access to a full Node.js environment. Practically, this means that you have a polyfilled `require` function that only has access to a limited set of APIs.

|Available API|Details|
|---|---|
|Electron modules|Renderer process modules|
|Node.js modules|[`events`](https://nodejs.org/api/events.html), [`timers`](https://nodejs.org/api/timers.html), [`url`](https://nodejs.org/api/url.html)|
|Polyfilled globals|[`Buffer`](https://nodejs.org/api/buffer.html), [`process`](https://www.electronjs.org/docs/latest/api/process), [`clearImmediate`](https://nodejs.org/api/timers.html#timers_clearimmediate_immediate), [`setImmediate`](https://nodejs.org/api/timers.html#timers_setimmediate_callback_args)|
For more information, check out the [Process Sandboxing](https://www.electronjs.org/docs/latest/tutorial/sandbox) guide.
- Preload scripts are injected before a web page loads in the renderer, similar to a Chrome extension's [content scripts](https://developer.chrome.com/docs/extensions/mv3/content_scripts/). To add features to your renderer that require privileged access, you can define [global](https://developer.mozilla.org/en-US/docs/Glossary/Global_object) objects through the [contextBridge](https://www.electronjs.org/docs/latest/api/context-bridge) API.
- 