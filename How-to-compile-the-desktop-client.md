# Step by step instructions

### 1. Clone the repo
```
$ git clone git@github.com:nextcloud/desktop.git
```

### 2. Create build directory:
```
$ cd desktop
$ mkdir build
```

### 3. Compile and install 

:information_source: **Optional** - depending on how you have your dev environment set up, you might need to define those paths as cmake flags or as environment variables:
* ```QTKEYCHAIN_LIBRARY```
* ```QTKEYCHAIN_INCLUDE_DIR```
* ```OPENSSL_ROOT_DIR```
* ```OPENSSL_INCLUDE_DIR```

:information_source: You can enable the build of the tests by setting the cmake flag ```BUILD_TESTING``` to ```1```.

:information_source: The cmake flag ```CMAKE_BUILD_TYPE``` has ```Debug``` and ```Release``` as options.

:warning: For development reasons it is better to **install the client on user space** instead on the global system. Mixing up libs/dll's of different version can lead to undefined behavior and crashes:

* You could use the **cmake flag** ```CMAKE_INSTALL_PREFIX``` as ```~/.local/``` in a **Linux** system. If you want to install system wide you could use ```/usr/local``` or ```/opt/nextcloud/```. 

* On **Windows 10** [```$USERPROFILE```](https://docs.microsoft.com/en-us/windows/deployment/usmt/usmt-recognized-environment-variables#a-href-idbkmk-2avariables-that-are-recognized-only-in-the-user-context) refers to ```C:\Users\<USERNAME>```.


## :penguin: Linux

### Generate the build files:
```
$ cd build
$ cmake .. -DCMAKE_INSTALL_PREFIX=~/nextcloud-desktop-client -DCMAKE_BUILD_TYPE=Debug -DNO_SHIBBOLETH=1
```

### Compile and install:
```
$ make install
```


## :door:  Windows

#### 3.2.1 Generate the build files:

```
$ cmake "-GVisual Studio 15 2017 Win64" .. -DCMAKE_INSTALL_PREFIX=$USERPROFILE\nextcloud-desktop-client -DCMAKE_BUILD_TYPE=Debug -DNO_SHIBBOLETH=1 
```

#### 3.2.2 Compile and install:
```
$ cmake --build . --config Debug --target install
```


## :apple: Mac OS

### Enable git submodules:
```
$ cd desktop
$ git submodule init
$ git submodule update
```

### Generate the build files:
```
$ cd build
$ cmake .. -DCMAKE_INSTALL_PREFIX=~/nextcloud-desktop-client -DCMAKE_BUILD_TYPE=Debug -DNO_SHIBBOLETH=1 
```

### Compile and install:
```
$ make install
```