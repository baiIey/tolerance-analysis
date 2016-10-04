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

### Building
Install Polymer project dependencies:
```
npm install -g gulp bower && npm install && bower install
```

Install [polymer-cli](https://github.com/Polymer/polymer-cli)
```
    npm install -g polymer-cli
```

### Start the development server

This command serves the app at `http://localhost:8080` and provides basic URL
routing for the app:

    polymer serve --open


### Build

This command performs HTML, CSS, and JS minification on the application
dependencies, and generates a service-worker.js file with code to pre-cache the
dependencies based on the entrypoint and fragments specified in `polymer.json`.
The minified files are output to the `build/unbundled` folder, and are suitable
for serving from a HTTP/2+Push compatible server.

In addition the command also creates a fallback `build/bundled` folder,
generated using fragment bundling, suitable for serving from non
H2/push-compatible servers or to clients that do not support H2/Push.

    polymer build

### Preview the build

This command serves the minified version of the app at `http://localhost:8080`
in an unbundled state, as it would be served by a push-compatible server:

    polymer serve build/unbundled

This command serves the minified version of the app at `http://localhost:8080`
generated using fragment bundling:

    polymer serve build/bundled

#### Run local server

The simplest probably is to use Pythons's built-in http server.

If you have [Python](http://python.org/) installed, it should be enough to run this from a command line:
```
# Python 2.x
python -m SimpleHTTPServer
```
```
# Python 3.x
python -m http.server
```

This will serve files from the current directory at localhost under port 8000:

http://localhost:8000/

Node.js has a simple HTTP server package. To install:
```
npm install http-server -g
```
To run:
```
http-server .
```
#### Environment
My current environment consists of [Atom](https://atom.io/), [Chrome Canary](https://www.google.com/chrome/browser/canary.html) and its [Developer Tools](https://developer.chrome.com/devtools), [Web Server for Chrome](https://chrome.google.com/webstore/detail/web-server-for-chrome/ofhbbkphhbklhfoeikjpcbhemlocgigb?hl=en), and [Git](https://git-scm.com/) in the command line.

In sum:
* A text editor and terminal shell
* Node.js version 6 or greater
* Bower
* Firebase CLI
* (optional) An Android device with the latest version of Chrome

### Dependencies
**App** dependencies in `public/index.html`.

**webcomponents-lite.js:** The Web Components polyfill, enabling your web components to have near full fidelity functionality on all browsers, even if they don't support Web Components.

**web-animations.min.js:** The Web Animations polyfill, enabling near full fidelity support for the emerging Web Animations platform specifications, even if they are not supported in the current browser.

**platinum-sw-elements.html:** A component that makes it trivial to configure and activate a service worker for a variety of use cases, using only HTML.

**firebase-app.html:** A component that makes it trivial to configure and initialize a Firebase app using only HTML.

**note-app.html:** Contains the core implementation of our app.

**Element** Dependencies in `public/tension-analysis-app.html`.

**na-elements.html:** This document pulls in pre-made view components for building the aesthetics and user interactions of our app.

**app-indexeddb-mirror.html:** This document contains a special element that will help us add offline data access to our Firebase data.

**polymerfire.html:** This document includes all of the elements needed to create a declarative relationship between our views and our Firebase data.
