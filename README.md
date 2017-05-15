# ThereVR

Check out our demo video at: [Demo](https://youtu.be/F5jgOfT--sU)

### Structure

ThereVR is split into two components, the Web Server and the Electron App. Commands to start each respective components will be split up into two sections.

### Web Server Structure (./therevr/)
- app/
  - components/ (Visual React Components)
  - containers/
    - AuthHoc/
      - sagas.js (Reduced Flux: Asynchronious state changers)
      - reducers.js (Reduced Flux: State changers)
      - selectors.js (Reduced Flux: Memo-ized states)
    (React Components that feed data into Visual React Components)
  - tests/ (general tests)
  - translations/ (in case we need multiple laguages)
  - utils/
    (Miscellaneous utility functions)
  - app.js (Entry point for front-end)
  - reducer.js (reducers config)
  - store.js (store config)
    - routes (route config)
    - internals (Scripts, build processes.)
    - server (more will be added to this folder)
- server/
  - config/ (All server config files live here)
  - controllers/
  - middlewares/ (Front-end middlewares)
  - models/
  - routes/
  - index.js (Entry point for the back-end)

### Electron App Structure (./therevr-electron/)
- index.js
  (Loads windows and handles FB login)
- streamer.js
  (Streams and encodes kinect data)
- sc.js
  (Injects code into the ThereVR web app.)
- therenect/
  - therenect.cpp (Interfaces kinect to Node.JS)

------------------------------------------------------------------------------------------

## ThereVR Web Server

The web application.
  
NOTE: Make sure you are in the ./therevr/ folder when running all these commands.

### Dependencies

  1. [Brew](https://brew.sh/)
  2. Node/NPM `brew install node`

### Starting ThereVR Server

  `npm install`
  `npm start`

ThereVR should be hosted on http://localhost:8000/, if that port is not available
then the application wil fail. Use the environment variable PORT to change the port
number.

------------------------------------------------------------------------------------------

## ThereVR-Electron

The native electron app. Used to transmit Kinect data over to the ThereVR website.
  
NOTE: Our application only supports MacOSX.
  
NOTE: Make sure you are in the ./therevr-electron/ folder when running all these commands.

### Dependencies

  1. [Brew](https://brew.sh/)
  2. FFMPEG `brew install ffmpeg`
  3. Node/NPM `brew install node`
  4. Node Modules `./npm-install.sh`

### Therenect
Therenect is the C++ node addon that allows for communication between Kinect and Node.JS

  `cd therenect && npm install && npm run build && cd ..`

### Starting ThereVR-Electron App

  `npm start`
