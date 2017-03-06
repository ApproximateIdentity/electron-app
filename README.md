Basic Electron App Example
==========================

This was created from the instructions here:

    https://electron.atom.io/docs/tutorial/quick-start/

Clone this repository to `electron-app/` (or whatever folder name you want). Make sure
you have elctron installed. You can do this using a nodeenv as follows:

```
$ nodeenv --prebuilt --node=4.2.3 nodeenv
$ source nodeenv/bin/activate
$ npm install -g electron
```

I doubt that the node version is very important (as long as it's not too old),
but this is the one I'm using now. Next you can run the app as follows:

```
$ electron electron-app/
```
