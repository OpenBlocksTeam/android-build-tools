# Eclipse Java Compiler
Eclipse Java Compiler (ecj) is a tool made by the Eclipse Foundation used to compile a java source code into java bytecode. Why use ecj instead of javac? Some said that ecj is easier to port into android compared to javac. At the time I'm writing this, noone has ever ported javac into android.

## How to
To run ecj, you **must** put the `ecj.jar` and `android.jar` (or the `android-24.jar` aswell, if you wanted to) file into the path that you get from `getFilesDir()`. Example use:
```java
String arguments = ""; // The arguments that we want to put
String android_jar_path = "android.jar"; // The path of android.jar we put, not sure what this is for, but well, termux put it sooo, we might aswell do it.

// -proc:none to disable annotation processing.
// -7 for java 1.7 compatibility.

String command =
"dalvikvm -Xmx256m -Xcompiler-option --compiler-filter=speed -cp ecj.jar org.eclipse.jdt.internal.compiler.batch.Main -proc:none -7 -cp " + android_jar_path + " " + arguments;

Runtime.getRuntime().exec(command);
```

Original `control` file:
```
Package: ecj
Architecture: all
Installed-Size: 8192
Maintainer: Termux members @termux
Version: 1:4.12-3
Homepage: http://www.eclipse.org/jdt/core/
Conflicts: ecj4.6
Description: Eclipse Compiler for Java
```
