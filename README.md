# react-native-relay

A working version of react-native with relay.

Fix the compatibility issue as described in https://github.com/facebook/relay/issues/26. 

## Getting Started 
- Clone the repo
  - `git clone https://github.com/lenaten/react-native-relay.git`
- Let relay client understand your schema
  - Copy your `schema.json` as generated from relay's `updateSchema.js` script to `data/schema.json`.
- Let relay client know your graphql server address
  - If you run your app in virtual machine or real device, you need to set your graphql address in index.android.js and index.ios.js. for example:
```
import Relay from 'react-relay';
Relay.injectNetworkLayer(
  new Relay.DefaultNetworkLayer('http://192.168.62.1:8080/graphql')
);
```
- Run your app
  - `react-native run-android` or start ios version via xcode.
- Rename your app
  - The default app name is "fix". If everything working as expected, feel free to rename the app.

## Modified Packages

- react-native
  - version: 0.13.0
  - changes: 
    - https://github.com/facebook/react-native/pull/3625
    - https://github.com/lenaten/react-native-relay/commit/bd06b2a5ead23cfb66a07baccb259ccfc9e04f0c
- relay
  - version: 0.4.0
  - changes: 
    - https://github.com/skevy/relay/tree/react-native
- fbjs
  - version: 0.4.0
  - changes: 
    - https://github.com/skevy/fbjs/tree/react-native

## TODO
- add basic graphql server for easy start

## Thanks
- @skevy. You did the real work.
- @boourns
