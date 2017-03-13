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

Packaging
---------

This basically just rehashes the instructions found here:

    https://electron.atom.io/docs/tutorial/application-distribution/

This app can be packaged for linux and Windows by following the following
steps:

1. Download the latest electron release from here (not the release that says
"symbols" in it...I'm not sure what that's about):

    ```
    https://github.com/electron/electron/releases/
    ```

2. Unzip that file into a folder called (say) `release/`.

3. Copy our simple app (i.e. the root reposistory folder which I call
`electron-app`) to the `resources` folder as follows (note that the
`release/resources/app` folder does not exist so the name of the folder
`electron-app` becomes `app`):

    ```
    cp -r electron-app release/resources/app
    ```

4. Finally if you execute the `release/electron` file it automatically finds
and starts your app.


Packaging App Using `asar` Format
---------------------------------

First install asar as follows:

```
    $ npm install -g asar
```

Next go into the `release/resources/` folder and pack the app as follows:

```
    $ asar pack app/ app.asar
    $ rm -r app/ # Remove old folder hierarchy
```

Next execute the electron application as before and it functions the same way.


Building a Debian Package Using Electron Builder
------------------------------------------------

Make sure that the following packages are installed:

```
# Run inside the root of the repository
$ npm install
```

After that package it with the following command to produce a debian package
inside of `dist/`:

```
$ npm run build
```
