For `zipalign`, The setup is basically the same thing as aapt, just replace aapt stuff with zipalign stuff

# AAPT
aapt is a tool that allows you to view, create, and update ZIP-compatible archives (ZIP, JAR, and APK). It can also compile resources into binary assets. It is the base builder for Android applications. ([Source](https://stackoverflow.com/questions/28234671/what-is-aapt-android-asset-packaging-tool-and-how-does-it-work))

## How to
To run aapt, you **must** put everything in this folder into the path that you get from `getFilesDir()` (Yes it can be a subdirectory).

Steps to use it:
 - chmod (change permission) the file so we can actually execute it
   ```java
   Runtime.getRuntime().exec("chmod u+x path/to/aapt"); // u = user, x = execute, + = add. "User add permission to execute" NOTE: This will NOT work on files outside getFilesDir()
   ```
 - well, run it
   ```
   Runtime.getRuntime().exec("path/to/aapt --arguments");
   ```

> Replace the `/path/to/aapt` to the path of aapt, and replace the `--arguments` to be the arguments that you want to put

Original `control` file:
```yml
Package: aapt
Architecture: aarch64
Installed-Size: 4524
Maintainer: Termux members @termux
Version: 7.1.2.33-11
Homepage: https://elinux.org/Android_aapt
Depends: libc++, libexpat, libpng, libzopfli, zlib
Description: Android Asset Packaging Tool
```

Thanks to Termux for providing this binary!
