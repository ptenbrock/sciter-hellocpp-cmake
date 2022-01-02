# Sciter hellocpp CMake example

This repository contains a copy of the [hellocpp](https://sciter.com/hello-cpp-tutorial/) example code of Sciter.JS, together with config files for CMake. This can serve as a basis for new projects using Sciter.

Currently, it only contains code for Linux & GTK3.

## Setup

Instead of a git submodule, there is a symbolic link to the Sciter SDK under `extern/sciter-js-sdk`. It is assumed, that the Sciter SDK lives in a folder called `sciter-js-sdk` next to this project. This can save a lot of space if multiple projects are using the SDK.

In order to build, you need to have the GTK3 headers on your machine. On Ubuntu, you can install them with:

```
sudo apt install libgtk-3-dev
```

## Build

Once everything is set up, you can build the project as usual:

```
mkdir build
cd build
cmake ..
make
```

## Run example

Run the executable inside the build directory:

```
./build/hellocpp
```
