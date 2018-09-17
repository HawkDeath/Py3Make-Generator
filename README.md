# Py3Make Generator

Py3Make Generator is a Makefile generator based on `build.json` file.

## build.json file structure

* `version` - number of iteration a build.json file
* `general` - basic information about project:
    * `appName` - name of application
    * `projectWorkspace` - a path to project workspace can be relative or not
* `code` - define an include directory and libs directory separate for Windows OS and Linux OS
    * `includeDir` - direction to include files in an extended library, example "/home/user/SFML-DEV/inlcude"
    * `libs` - names of extended or standard libraries using in project
* `debug` - define a flags and defines for debug mode
* `release` - define a flags and defines for release mode


## Usage:
* python3 build.py init - initializes a workspace and generate a `.builddb` catalog and file database with extensions: `[.cpp, .cxx, .cc, .c]`

* python3 build.py update - generates a Makefile base on `build.json` file

### Makefile targets:
* all - build in debug and release mode
* debug - build only in debug mode
* release - build only in release mode
* clean - clean a debug and release outputs
* debug-clean - clean a debug output
* release-clean - clean a release output

## TODO:
* Possibility to skip catalogs and/or files
* New targets - generate a library static/dynamic
* Support for sub-targets
* Scripts .sh and .bat to automatic build
* Support to link MSVC library (.lib)
