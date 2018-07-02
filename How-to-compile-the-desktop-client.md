# Requirements

## General
- OpenSSL 1.1.x
- QtKeychain
- Qt 5.x.x
- zlib

## Windows
- OpenSSL 1.1.x binaries: https://indy.fulgan.com/SSL/
- QtKeychain - compile and install from https://github.com/frankosterfeld/qtkeychain
- zlib binaries: https://github.com/maxirmx/Dist_zlib
- Visual Studio 
- Recommended: Git bash (it comes with Git)

## mac OS
- XCode...

# Step by step instructions

## 1. Clone the repo
```
$ git clone git@github.com:nextcloud/desktop.git
```

## 2. Create build directory:
```
$ cd desktop
$ mkdir build
```

## 3. Compile and install
You may pick the CMAKE_BUILD_TYPE - Debug or Release.

Tip: If you already have the desktop client installed from another source (snap etc) in your system, make sure the compiled version is installed in a different path. Mixing up libs/dll's of different version can lead to undefined behavior and crashes.

### 3.1 Linux

#### 3.1.1 Generate the build files:
```
$ cmake .. -DCMAKE_INSTALL_PREFIX=path-to-install-folder/ -DCMAKE_BUILD_TYPE=Debug -DNO_SHIBBOLETH=1
```

#### 3.1.2 Compile and install:
```
$ make install
```

### 3.2 Windows

#### 3.2.1 Generate the build files:

```
$ cmake -G "Visual Studio 15 2017 Win64" .. -DCMAKE_INSTALL_PREFIX=path-to-install-folder/ -DCMAKE_BUILD_TYPE=Debug -DNO_SHIBBOLETH=1
```

#### 3.2.2 Compile and install:
```
$ cmake --build . --config Debug --target install
```

### 3.3 Mac OS

#### 3.1.1 Generate the build files:
```
$ cmake .. -DCMAKE_INSTALL_PREFIX=path-to-install-folder/ -DCMAKE_BUILD_TYPE=Debug -DNO_SHIBBOLETH=1
```

#### 3.1.2 Compile and install:
```
$ make install
```










