# Tolerance Analysis
[Tolerance analysis](https://en.wikipedia.org/wiki/Tolerance_analysis) is the general term for activities related to the study of potential accumulated variation in mechanical parts and assemblies.

Tolerance stackups or tolerance stacks are used to describe the problem-solving process in mechanical engineering of calculating the effects of the accumulated variation that is allowed by specified dimensions and tolerances.

### Firebase and Polymer Web Components
This prototype is a progressive web app using Firebase and Polymer Web Components.

 [Firebase](https://firebase.google.com/) allows us to connect pre-made view components to data components to build an app that features user authentication, a database backend, offline data availability and the ability to be installed to the home screen of an Android device.

 The [Polymer Project](https://www.polymer-project.org/1.0/) is a library that uses the latest web technologies to create custom HTML elements.

 (The declarative nature, the encapsulation, the data bindings, the attribute and event-driven APIs are all orders of magnitude simpler than existing JavaScript / HTML UI element componentization. The reusability of a custom element compared to an HTML snippet with some associated JavaScript and CSS cannot be overstated.)

Combined, this framework allows for a full-fidelity, offline-capable progressive web app.

To recap:

* Used Firebase components to add database backend
* Used Firebase components to add user authentication
* Keeps user data available when the user goes offline
* Deployed app to Firebase hosting
* Made  app installable to the home screen of an Android device

### A brief introduction to Service Worker
[Service Worker](https://developers.google.com/web/fundamentals/primers/service-worker/) is a type of Web Worker that runs in the background behind a web app, even when the web app that loaded the service worker is not open or running on the user's device. It is able to do a lot of things, but most importantly for us, it has two amazing features:

* It can control how files in a web app are cached.
* It can make cached files available even when the app is opened while the user is offline.

*Polymer + Service Worker = 💕*

### Building and Running
 You'll need a static web server to preview the files in the public directory as you are working on them.

My current environment consists of [Atom](https://atom.io/), [Chrome Canary](https://www.google.com/chrome/browser/canary.html) and its [Developer Tools](https://developer.chrome.com/devtools), [Web Server for Chrome](https://chrome.google.com/webstore/detail/web-server-for-chrome/ofhbbkphhbklhfoeikjpcbhemlocgigb?hl=en), and [Git](https://git-scm.com/) in the command line.

In sum:
* A text editor and terminal shell
* Node.js version 6 or greater
* A Google account
* (optional) An Android device with the latest version of Chrome

To build:
* Node.js
* Bower
* Firebase CLI

### Dependencies
**webcomponents-lite.js:** The Web Components polyfill, enabling your web components to have near full fidelity functionality on all browsers, even if they don't support Web Components.

**web-animations.min.js:** The Web Animations polyfill, enabling near full fidelity support for the emerging Web Animations platform specifications, even if they are not supported in the current browser.

**platinum-sw-elements.html:** A component that makes it trivial to configure and activate a service worker for a variety of use cases, using only HTML.

**firebase-app.html:** A component that makes it trivial to configure and initialize a Firebase app using only HTML.

**note-app.html:** Contains the core implementation of our app.
