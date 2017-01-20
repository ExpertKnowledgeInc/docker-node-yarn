# node-yarn

## Description

This image is based on official [node image](https://hub.docker.com/_/node/).

Currently supported tags:
* latest
* latest-onbuild
* argon
* argon-onbuild
* boron
* boron-onbuild

Feel free to create an issue if you need more images.

## Usage

```
docker run expertknowledge/node-yarn
```

## Onbuild images
Those images will copy your package.json and yarn.lock file from directory to /src directory and install your node packages in /node_modules (for ease of development with volumes). 
