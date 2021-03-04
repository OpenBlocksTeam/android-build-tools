# Dx
Dx is an old tool used to convert a java bytecode into dalvik (If you want a newer one, use d8), making it possible to run java classes on android.

## How to
To run dx, you **must** put the `dex.jar` file into the path that you get from `getFilesDir()`. Then, to execute it, use
```java
Runtime.getRuntime().exec("dalvikvm -Xcompiler-option --compiler-filter=speed -Xmx256m -cp /path/to/dx.jar dx.dx.command.Main \"!arguments!\"");
```
> Replace the `/path/to/dx.jar` to the path of dx.jar, and replace the `!arguments!` to be the arguments that you want to put

> To merge dexes, replace the `dx.dx.command.Main` to be `dx.dx.merge.DexMerger` 

Original `control` file:
```yml
Package: dx
Architecture: all
Installed-Size: 1472
Maintainer: @termux
Version: 1:1.16-6
Homepage: http://developer.android.com/tools/help/index.html
Description: Command which takes in Java class files and converts them to format executable by Dalvik VM
```
