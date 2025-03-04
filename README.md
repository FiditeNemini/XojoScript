# /simulanics/XojoScript

An open-source XojoScript compiler and virtual machine for the Xojo language. Compile and Run XojoScript at native C++ machine-code speed, on any system or architecture supporting C++ compilers [GNU/GCC/G++/clang]. This includes 99.9% of devices - even the web [using emscripten]! 🙏

# XojoScript Bytecode Compiler and Virtual Machine 🚀

Welcome to the **XojoScript Bytecode Compiler and Virtual Machine**! This project is a bytecode compiler and virtual machine written in C++ that handles XojoScript execution—including functions, classes, and more - entirely cross-platform. It compiles XojoScript into bytecode and executes it on a cross-platform custom virtual machine. 🤯

## Features ✨

- **Cross-platform Plugin Support:** Compile and place plugins in a "libs" directory located beside the xojoscript executable. Plugins will automatically be found, loaded, and ready for use in your xojoscripts.
- **Cross-platform Library Support:** Load system-level APIs using 'Declare' and use them as you would in Xojo.
- **Function Support:** Compile and execute user-defined functions and built-in ones. Overloading of functions is permitted.
- **Module Support:** Create XojoScript Modules. ("extends" is in the works).
- **Class & Instance Support:** Create classes, define methods, and instantiate objects.
- **Intrinsic Types:** Handles types like Color, Integer, Double, Boolean, Variant and String.
- **Bytecode Execution:** Runs compiled bytecode on a custom VM.
- **Debug Logging:** Step-by-step debug logs to trace lexing, parsing, compiling, and execution.
- **Intuitive Syntax:** Matches Xojo language syntax (Currently, functions require parenthesis - this is strictly for debugging purposes as other datatypes are added and tested. Parenthesis will be optional at a later date, as in Xojo's implementation, for interoperability and consistency.)
- **Open Source:** Released under the MIT License.

## Getting Started 🏁

### Prerequisites

- A C++ compiler with C++17 support (e.g. g++, clang++)
- Git
- libffi (https://github.com/libffi/libffi) - handles cross-platform plugin and system-level API access.
- (Optional) Rust/Go/C#/etc - to build plugins using other languages than C++

### Installation

1. **Clone the Repository:**

   ```bash
   git clone https://github.com/simulanics/XojoScript
   cd XojoScript
   ```
2. Compile the Project:

For example, using g++:

```
g++ -std=c++17 -o xojoscript xojoscript.cpp -lffi
```

With speed optimizations:

```
g++ -o xojoscript xojoscript.cpp -lffi -O3 -march=native -mtune=native -flto
```

3. Prepare Your Script:

Create a file named test.txt with your XojoScript code. For example:

```
Function addtwonumbers(num1 As Integer, num2 As Integer) As Integer
    Return num1 + num2
End Function

Public Sub Main()
    Dim result As Integer = addtwonumbers(2, 3)
    Print(str(result))
End Sub
```

`Main() is reserved for GUI applications primarily, but is not strictly for this purpose. Xojo's implementation of XojoScript does not contain this natively, but this Sub() acts as each OS XojoScript's program entry-point if supplied, and will be executed before any other top-down code.`

4. Run the Compiler on a script:

```
./xojoscript --s filename
```

Debugging 🔍

Debug trace and profile logging is enabled via the DEBUG_MODE "--d true/false" commandline flag. Set it to true or false to enable debugging:

```
./xojoscript --s filename --d true > debugtrace.log
```

`It is recommended to write debugtrace profiling to a file for analysis, as even simple program trace profiles may be many hundred megabytes as each logical step and potential errors or warnings are recorded.`

This will output detailed logs for lexing, parsing, compiling, and execution.

Contributing 🤝

Contributions are welcome! Please feel free to open issues or submit pull requests. Your help is appreciated! 🎉

License 📄

This project is licensed under the MIT License. See the LICENSE file for details.

---

🤗 Happy Coding! 😄



