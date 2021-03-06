# **NAME**IT

**NAME**IT is a free, open-source, file naming app. It allows you to fetch series data from TVDB and name files


## Installation
The easiest way is to go to the [**NAME**IT](https://tallic.github.io/name-it/) homepage and download the binary for your system.

Building the project from source requires *node*.

Check out the project and install the dependencies:
```
npm install
``` 

Then build the electron app with 
```
npm run electron:build
```
with the build binary located in `name-it/build`.

## Usage
The left pane represents the episodes with which the files will be named.
Click on the search icon, search for a series, and select a season that you want to use as a reference.

The right pane contains your files.
Click on the folder and select multiple files that belong to one season that you want to rename.

Remove episodes (left pane) and reorder the files (right pane) such that the episodes match the file order.
Finally, click rename to rename the files.

You can change the language of the episodes or the renaming format in the settings.
There are preconfigured examples that make clear how the naming formatting works.
Also, you can define your template.


## Feature Requests & Issues
This project is only a small vacation relaxation project to play around with some technology.
Furthermore, I needed a replacement for [FileBot](https://www.filebot.net/) as it changed to a quite expensive proprietary license. 
I will fix bugs and add requested features but only if I deem useful and have time.

Just submit an issue or feel free to fork and adapt the project as needed.

## Package & Publish
To packaging and publishing is currently done manual via a docker container and release-it script:
```
docker run --rm -ti  --env-file <(env | grep -iE 'DEBUG|NODE_|ELECTRON_|YARN_|NPM_|CI|CIRCLE|TRAVIS_TAG|TRAVIS|TRAVIS_REPO_|TRAVIS_BUILD_|TRAVIS_BRANCH|TRAVIS_PULL_REQUEST_|APPVEYOR_|CSC_|GH_|GITHUB_|BT_|AWS_|STRIP|BUILD_')  --env ELECTRON_CACHE="/root/.cache/electron"  --env ELECTRON_BUILDER_CACHE="/root/.cache/electron-builder"  -v ${PWD}:/project  -v ${PWD##*/}-node-modules:/project/node_modules  -v ~/.cache/electron:/root/.cache/electron  -v ~/.cache/electron-builder:/root/.cache/electron-builder  electronuserland/builder:wine
```
In the container install the dependencies and start the packing:
```
yarn
yarn electron:build
```


## Authors
* Hannes Thaller

## License
MIT
