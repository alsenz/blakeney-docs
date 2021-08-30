# Blakeney by Example

This guide introduces the core language features of Blakeney by means of worked exampled:

## Hello World!

One of the most basic programs in Blakeney is the omnipresent "Hello World" example:

    package examples
    
    def main() -> int:
        std.print("Hello, world!")
        return 0

!!! Walkthrough
    
    __line 1__ `package examples`:
    _Tells the code packaging system that this code forms part of the `examples` package_
    
    __line 3__ `def main() -> int`:
    _This is the main function of the program. Returns the program exit code._
    
    __line 4__ `print("Hello, world!")`:
    _This is a call to the [standard library](std-library). It writes the string to stdout._
    
    __line 5__ `return 0`:
    _Tell the operating system that the program exited normally._

### The "main" function

Every application needs a `main()` function. It must return a single value of type `int`, which indicates the program's exit code.

The `main()` function is the function that the program calls when it runs. You can only have __one__ `main` function per package. Other packages, and other files in the same package, do not need to have a `main` function so long as the compiler is provided one elsewhere. You can tell the compiler which package has the main function using the `--main-package` argument:

    blakeneyc --main-package examples src/*.bky

It is perfectly normal to have multiple main functions from other packages in your program, the compiler will just ignore these.

##### Related material

 1. [Functions]()
 2. [Standard library]()
 3. [Globals]()
 4. [Packages]()


