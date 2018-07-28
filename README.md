## Maya Math Nodes
Collection of math nodes for Autodesk Maya

#### Building
To build the library on Windows, clone the repository and navigate to the cloned directory,
then run the following commands:

```
mkdir build
cd build
cmake ../. -G "Visual Studio 15 2017 Win64"
```

This will generate a Visual Studio solution you can use to build.

To build the library on OSX or Linux use the following commands:

```
mkdir build
cd build
cmake ../. -G "CodeBlocks - Unix Makefiles"
make
```

The build looks for Maya in the default installation directory for each platform, however you can always provide it with a custom path:

```
-DMAYA_LOCATION=/apps/autodesk/
```

Likewise, the build defaults to Maya version 2018, this can be changed as follows:

```
-DMAYA_VERSION=2017
```

#### Installation
To install the library on OSX or Linux run the following command:

```
make install
```

By default the resulting module gets installed under the current build directory.

To make the module available in Maya, add the install location to *MAYA_MODULE_PATH* environment variable or create
a symlink to the *MayaMathNodes.mod* under an an existing module path.

The install location can also be changed as follows:

```
-DINSTALL_DIR=/preffered/install/directory
```

#### Testing
In order to run the test suite, execute the *mayapy* interpreter and pass the *tests* directory as an argument, for example:

```
/Applications/Autodesk/maya2018/Maya.app/Contents/bin/mayapy tests
```
