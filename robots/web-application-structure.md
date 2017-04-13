# Nodebot/Web-Powered Robot Application Structure

## An example architecture for all your apps and robots connected to them.
*NOTE: Only for prototypes and local projects! If you have an answer for production environments, feel free to add an answer!*

All of the app, server, and robot scripts should be placed under the `src` directory.

This is an example stack of what I've been using in my prototyping projects.

```
project
  └--src
  |   └--client
  |   |   └--app.js
  |   |   └--all client side scripts go here.
  |   └--robot
  |   |   └--all robot scripts go here
  |   └--server
  |   |   └--index.js
  |   |   └--render-app.js
  |   └--shared
  |   |   └--all shared files for server, client, config etc. go here
  └--package.json
  └--.babelrc
  └--.eslintrc.json
```

Under `src`, there's a few main directories:

- `client` — the application front end and all scripting for the UI. Examples would be `.js` and `.jsx` for building the DOM and Client providers.
- `robot` — usually all scripting for the robot will be placed on the server level. However, additional scripts i.e. JavaScript classes and objects for the robot should be placed here then imported to the same level as the robot.
- `server` — all server actions and scripts are placed here, but should the server receive any actions or payloads from the client that interact with the robot then the robot should work from this level.
  - `render-app` is a file containing an ES6 string with all the app's HTML — this is useful for Universal rendering but also placing shared scripts and components into the app and using it as a view for Express.
- `shared` — should anything required for the client, server, and/or robot scripts should be placed in here. Including any utilities and configurations.
