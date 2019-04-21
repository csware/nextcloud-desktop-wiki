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

:information_source: _Optional - you may or may not get errors if you don't define those cmake flags:_

* ```-DCMAKE_BUILD_TYPE=$TYPE```
* ```-DQTKEYCHAIN_LIBRARY=$PATH/lib/$LIBFILE```
* ```-DQTKEYCHAIN_INCLUDE_DIR=$PATH/include/qt5keychain/```
* ```-DOPENSSL_ROOT_DIR=$PATH/```
* ```-DOPENSSL_INCLUDE_DIR=$PATH/include -DOPENSSL_LIBRARIES=$PATH/lib```

:warning: _Do not forget:_
* _Replace ```$PATH``` and ```$LIBFILE``` by the correct path in your system._
* _Replace ```$TYPE``` by ```Release``` or ```Debug```._
* _If you pick ```Debug``` you may also want to enable the build of the tests by setting the flag ```-DBUILD_TESTING=1```._

:information_source: _If you already have the desktop client installed from another source (snap etc) in your system, make sure the compiled version is installed in a different path. Mixing up libs/dll's of different version can lead to undefined behavior and crashes._


## :penguin: Linux

### Generate the build files:
```
$ cd build
$ cmake .. -DCMAKE_INSTALL_PREFIX=~/desktop-install/ -DCMAKE_BUILD_TYPE=$TYPE -DNO_SHIBBOLETH=1
```

### Compile and install:
```
$ make install
```


## :door:  Windows

#### 3.2.1 Generate the build files:

```
$ cmake "-GVisual Studio 15 2017 Win64" .. -DCMAKE_INSTALL_PREFIX=$PATH -DCMAKE_BUILD_TYPE=$TYPE -DNO_SHIBBOLETH=1 
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
$ cmake .. -DCMAKE_INSTALL_PREFIX=$PATH -DCMAKE_BUILD_TYPE=$TYPE -DNO_SHIBBOLETH=1 
```

### Compile and install:
```
$ make install
```