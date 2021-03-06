# Py3Make Generator

Py3Make Generator is a Makefile generator based on `build.json` file.

## build.json file structure

* `version` - number of iteration a build.json file
* `compiler` - program to compile, you can use `gcc, g++, clang, etc.`
* `general` - basic information about project:
    * `appName` - name of application
    * `projectWorkspace` - a path to project workspace can be relative or not
* `code` - define an include directory and libs directory separate for Windows OS and Linux OS
    * `includeDir` - direction to include files in an extended library, example "/home/user/LIB-DEV/inlcude"
    * `libs` - names of extended or standard libraries using in project
        * `msvc-lib` - path to MSVC library (only Windows support), example `"msvc-lib": [ "C:\\sdk\\VulkanSDK\\1.1.82.0\\Lib\\vulkan-1.lib" ],`
* `debug` - define a flags and defines for debug mode
* `release` - define a flags and defines for release mode


## Usage:
* python3 build.py generate - generates a Makefile base on `build.json` file. Generates a `.builddb` catalog and file database with extensions: `[.cpp, .cxx, .cc, .c]`.
* `--settings` or `-s` parameter set a directory to `build.json` file

### Recommended:
Use a `build.sh` or `build.bat` to automatic update a workspace and run a compile a program. Targets like below.

### Makefile targets:
* all - build in debug and release mode
* debug - build only in debug mode
* release - build only in release mode
* clean - clean a debug and release outputs
* debug-clean - clean a debug output
* release-clean - clean a release output

## TODO:
* ~~`--settings` an argument to set point a `build.json` file~~
* Possibility to skip catalogs and/or files
* New targets - generate a library static/dynamic
* Support for sub-targets
* Checking changes in config file
* ~~Scripts .sh and .bat to automatic build~~
* ~~Support to link MSVC library (.lib)~~
* ~~Code refactor~~

## Know issues
* The script does not include changes to the .json file after create `.builddb` catalog
