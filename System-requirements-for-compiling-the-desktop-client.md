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
- Png2Icon - you need to use this version: https://github.com/hiiamok/png2ImageMagickICO

## Linux 
On Ubuntu 18.04 (same in 16.04):
- openssl
- libssl-dev
- libzip-dev
- qtdeclarative5-dev
- qtwebengine5-dev
- qt5keychain-dev
- qttools5-dev
- sqlite3
- libsqlite3-dev
- libqt5svg5-dev
- libkf5kjs-dev (optional)
- doxygen (optional)

Install via terminal using this command:
```
sudo apt install openssl libssl-dev libzip-dev qtdeclarative5-dev qtwebengine5-dev qt5keychain-dev qttools5-dev sqlite3 libsqlite3-dev libqt5svg5-dev
```
And if you want to add the optional dependencies too:
```
sudo apt install libkf5kjs-dev doxygen
```

For Nautilus integration:
```
sudo apt install python-nautilus
wget -O ~/.local/share/nautilus-python/extensions/syncstate-Nextcloud.py "https://raw.githubusercontent.com/nextcloud/desktop/master/shell_integration/nautilus/syncstate.py"
```

If you need Dolphin integration:
- libkf5config-dev
- kio-dev extra-cmake-modules

## mac OS
- XCode...
- brew
- OpenSSL 1.1.x (brew install openssl@1.1)
- QtKeychain (brew install qtkeychain)
- Qt 5.x.x












