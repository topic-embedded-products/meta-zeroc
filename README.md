# OpenEmbedded/Yocto Layer for ZeroC

This meta layer provides recipes for ZeroC products.

## Branches

This respository has several branches as the poky repository (warrior, thud, sumo, jethro, krogoth, morty, etc.)
development is done in the master branch, and other branches must be used for building with
a specific poky release.

## Usage

See the OpenEmbedded [Layers FAQ](http://www.openembedded.org/wiki/Layers_FAQ) for instructions on adding a new layer to your project.

## Recipes

### zeroc-ice

This recipe provides [Ice](https://github.com/zeroc-ice/ice). It is configured as a split recipe containing the following packages:

| Package Name        | Contents                                              |
| ------------        | --------                                              |
| zeroc-ice           | Ice for C++ shared libraries                          |
| zeroc-ice-dev       | Ice for C++ header files and Slice compilers          |
| zeroc-ice-doc       | Man file documentation                                |
| zeroc-ice-python3   | Ice for Python                                        |
| zeroc-ice-slice     | Slice files                                           |
| zeroc-ice-staticdev | Ice for C++ static libraries                          |
| zeroc-ice-utils     | Ice utilities and admin tools                         |
| zeroc-glacier2      | Glacier2 router                                       |
| zeroc-icebox        | IceBox server                                         |
| zeroc-icegrid       | IceGrid service                                       |
| zeroc-icepatch2     | IcePatch2 service                                     |
| zeroc-icestorm      | IceStorm publish-subscribe event distribution service |
| zeroc-icebridge     | IceBridge server                                      |

`native` and `nativesdk` packages are also available.

### zeroc-image-testing

This recipe provides an image configured with the packages needed to run the Ice test suite. A `-dev` version is also available which installs development (`-dev`) packages.

Note that you will need to [install pip manually](https://pip.pypa.io/en/latest/installing.html) once your image is running if you wish to run the glacier2 tests.

## Classes

### zeroc-icenative37

This class adds the `zeroc-ice` native development dependency and defines the following variables:

| Variable            | Description                               |
| --------            | -----------                               |
| ZEROC_ICE_SLICE2CPP | Path to the native `slice2cpp` executable |
| ZEROC_ICE_SLICE2PY  | Path to the native `slice2py` executable  |
| ZEROC_ICE_SLICE_DIR | Directory containing Slice files          |
| ZEROC_ICE_VERSION   | `zeroc-ice` Version                       |
