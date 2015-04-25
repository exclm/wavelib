## How to integrate wavelib in your code ##
WAVELIB code consisted of 6 C source files and their corresponding headers at the last count. You can directly use these files in your code by including "wavelib.h" header in your code. (Note - There are two wavelib.h files. One in the src folder and the other in the header folder. If you are using just the source files without building a library then ignore the header folder and the wavelib.h file in that folder. That file is to used only if you have created a separate library) . Just make sure that all 54 files are in the same folder and your program can "see" them. For example, something like

```
gcc -Wall -c *.c 
```

will work with GNU gcc compiler. It will build object files of all 27 files in the /src folder and you can link your project against these object files. This is more straightforward if you are using one of the modern IDEs as you can just plug all the 54 files in your code and just link "wavelib.h" to your project files. The IDE will do the rest. If you are an expert programmer then you may want to skip the rest of this section.

### Building Shared and Static Libraries on Linux ###

**A Simple Static Library**

If you are using GNU GCC compiler then something like

```
gcc -c *.c
```

will build the object files in the src folder. You can then package the object files in a wavelib.a static library package using

```
ar rcs libwavelib.a *.o
```

**A Simple Shared Library**

```
    gcc -fPIC -c *.c
    gcc -shared -Wl,-soname,libwavelib.so.1 -o libwavelib.so.1.0   *.o

```

You may want to move libwavelib.so.1.0 to a separate folder before creating symlinks.

```
ln -sf libwavelib.so.1.0 libwavelib.so
ln -sf libwavelib.so.1.0 libwavelib.so.1
```

If your folder is not on the path then you will have to export the path before executing your program.

```
export LD_LIBRARY_PATH=/wavelibFOLDERLOCATION/
```

Some useful links.

http://www.yolinux.com/TUTORIALS/LibraryArchives-StaticAndDynamic.html

http://codingfreak.blogspot.com/2010/01/creating-and-using-static-libraries-in.html

http://www.techytalk.info/c-cplusplus-library-programming-on-linux-part-one-static-libraries/

http://www.techytalk.info/c-cplusplus-library-programming-on-linux-part-two-dynamic-libraries/

### Building Shared and Static Libraries on Windows ###

**Use IDE to build the libraries**

I am mentioning this approach as most Windows programmers use one or more IDEs for their programming. All modern IDEs can create static and DLLs from source codes. eg., In Visual Studio you start out by creating an empty project, then adding all the source ad header files followed by "Build Solution".

Link - http://msdn.microsoft.com/en-us/library/ms235636.aspx

http://msdn.microsoft.com/en-us/library/ms235627.aspx

It is equally straightforward to create libraries in Eclipse , Codeblocks and other IDEs.

**Working with Cygwin**

A Static library (**.a) build is identical to that with linux.**

**A Simple Static Library**

If you are using GNU GCC compiler then something like

```
gcc -c *.c
```

will build the object files in the src folder. You can then package the object files in a libwavelib.a static library package using

```
ar rcs libwavelib.a *.o
```


**A Simple DLL in Cygwin**

This will build a simple standalone DLL.

```
gcc -c -fPIC *.c
gcc -shared -o libwavelib.dll *.o
```

Check this link for more options, specially if you want to build the DLL as an export library.

http://cygwin.com/cygwin-ug-net/dll.html

**The File wavelib.h from the header folder should be used with the library
that you just build**