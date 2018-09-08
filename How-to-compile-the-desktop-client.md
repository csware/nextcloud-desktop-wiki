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
cmake "-GVisual Studio 15 2017 Win64" .. -DCMAKE_INSTALL_PREFIX=path-to-install-folder/ -DCMAKE_BUILD_TYPE=Debug -DNO_SHIBBOLETH=1 -DQTKEYCHAIN_LIBRARY=/path-to-qt5keychain-folder/lib64/libqt5keychain.so -DQTKEYCHAIN_INCLUDE_DIR=/path-to-qt5keychain-folder/include/qt5keychain/ -DOPENSSL_ROOT_DIR=/path-to-openssl-folder/ -DOPENSSL_INCLUDE_DIR=path-to-openssl-folder/include -DOPENSSL_LIBRARIES=path-to-openssl-folder/lib
```

#### 3.1.2 Compile and install:
```
$ make install
```

### 3.2 Windows

#### 3.2.1 Generate the build files:

```
$ cmake "-GVisual Studio 15 2017 Win64" .. -DCMAKE_INSTALL_PREFIX=path-to-install-folder/ -DCMAKE_BUILD_TYPE=Debug -DNO_SHIBBOLETH=1 -DPng2Ico_EXECUTABLE=/path-to-install-png2ico/png2ico.exe  -DQTKEYCHAIN_LIBRARY=/path-to-qt5keychain-folder/lib/qt5keychain.lib -DQTKEYCHAIN_INCLUDE_DIR=/path-to-qt5keychain-folder/include/qt5keychain/ -DOPENSSL_ROOT_DIR=/path-to-openssl-folder/ -DOPENSSL_INCLUDE_DIR=path-to-openssl-folder/include -DOPENSSL_LIBRARIES=path-to-openssl-folder/lib
```

#### 3.2.2 Compile and install:
```
$ cmake --build . --config Debug --target install
```

### 3.3 Mac OS

#### 3.1.1 Enable git submodules:
```
$ cd desktop
$ git submodule init
$ git submodule update
```

#### 3.1.2 Generate the build files:
```
$ cd build
$ cmake .. -DCMAKE_INSTALL_PREFIX=path-to-install-folder/ -DCMAKE_BUILD_TYPE=Debug -DNO_SHIBBOLETH=1 -DQTKEYCHAIN_LIBRARY=/path-to-qt5keychain-folder/lib/libqt5keychain.dylib -DQTKEYCHAIN_INCLUDE_DIR=/path-to-qt5keychain-folder/include/qt5keychain/ -DOPENSSL_ROOT_DIR=/path-to-openssl-folder/ -DOPENSSL_INCLUDE_DIR=path-to-openssl-folder/include -DOPENSSL_LIBRARIES=path-to-openssl-folder/lib
```

#### 3.1.2 Compile and install:
```
$ make install
```