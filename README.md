# piper-android
This fork simply adds android build support, intended for use in https://www.curseforge.com/minecraft/mc-mods/narrator with https://github.com/AngelAuraMC/Amethyst-Android/actions

### Compiling
Ye ole generic cmake command as documented in [official android docs](https://developer.android.com/ndk/guides/cmake) works. Here's a sample for statically linked Android 5.0 arm64-v8a, with install directory
```bash
cmake . -DCMAKE_TOOLCHAIN_FILE=$ANDROID_NDK_HOME/build/cmake/android.toolchain.cmake -DANDROID_PLATFORM=android-21 -DANDROID_ABI=arm64-v8a -DANDROID_STL=c++_static -DCMAKE_INSTALL_PREFIX=$PWD/install -B build-cmake
```
As per tradition, `make clean` doesn't really work if you wanna change the cmake settings for architecture, stl, etc. You'll have to make a bunch manually.
To minimize the amount of clones, there exists a branch that uses submodules instead ([master-but-submodules](https://github.com/alexytomi/piper-android/tree/master-but-submodules)). Feel free to use this for development.
If you're looking for the modern, official, updated piper: https://github.com/OHF-Voice/piper1-gpl
