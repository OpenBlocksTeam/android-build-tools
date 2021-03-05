# D8
D8 is a tool used to convert a java bytecode into dalvik code, making it possible to run java classes on android. It is similar to dx, but D8 runs faster and produces smaller .dex files with equivalent or better runtime performance when compared to dx.

## How to
To run d8, you **must** put the `d8.jar` file into the path that you get from `getFilesDir()`. Then, to execute it, use
```java
Runtime.getRuntime().exec("dalvikvm -Xcompiler-option --compiler-filter=speed -Xmx256m -cp /path/to/d8.jar com.android.tools.r8.D8 \"!arguments!\"");
```
> Replace the `/path/to/d8.jar` to the path of d8.jar, and replace the `!arguments!` to be the arguments that you want to put

This jar is built from source at version 2.1.89 and converted into dex code using d8 itself, click [here](https://r8.googlesource.com/r8/+/refs/tags/2.1.89) to view the source
