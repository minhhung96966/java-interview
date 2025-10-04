## Java platform interview preparation

### Java is Platform-Independent
- Write once, run anywhere (WORA) principle.
- Ability of a software to run on different operating systems without modification.
- How Java achieves it: Java Virtual Machine (JVM) runs the same bytecode on any OS.
- A Java program complied on Windows can run on Linux or Mac without recompilation.
- When compiled:
  - The Java compiler (javac) compiles Java source code (.java files) to bytecode (.class files).
  - You can run the same `.class` files (bytecode) on any platform with a compatible JVM (Windows JVM, Linux JVM, MacOS JVM, etc.).
  - The JVM interprets the bytecode and translates it into machine code specific to the underlying operating system and hardware architecture.
- C/C++ programs are compiled to machine code specific to the target platform, making them platform-dependent, need to recompile for each platform.
  - Portability: Ability to run on different platforms with minimal changes, but still requires recompilation.
  - C/C++ are portable but not platform-independent.
  - Java is both portable and platform-independent.
  - Assembly language is neither portable nor platform-independent, as it is specific to a particular CPU architecture.
- Python and JavaScript are interpreted languages, which means they are executed by an interpreter rather than being compiled to machine code. However, they are not platform-independent in the same way as Java:
  - Python: The Python interpreter must be installed on the target platform, and different versions of Python may have compatibility issues.
  - JavaScript: JavaScript is primarily executed in web browsers, and different browsers may have varying levels of support for JavaScript features.

### Code vs machine code vs bytecode
- Code: Human-readable instructions written in a programming language (e.g., Java, C, Python).
- Machine code: Low-level binary instructions that a computer's CPU can execute directly (contains 0s and 1s).
- Bytecode: Intermediate code that is more abstract than machine code but not as high-level as source code. Java bytecode is executed by the JVM.
- Java code is compiled to bytecode, which is then interpreted or compiled to machine code by the JVM at runtime.
- C/C++ code is compiled directly to machine code specific to the target platform.
- Python code is interpreted by the Python interpreter, which translates it to machine code at runtime.
- JavaScript code is interpreted by web browsers or JavaScript engines, which translate it to machine code at runtime.
- Assembly language is a low-level programming language that is specific to a particular CPU architecture. It is not portable and must be assembled to machine code for each target platform.
- Java is platform-independent because it uses bytecode and the JVM, while C/C++ are platform-dependent because they compile directly to machine code specific to the target platform.

### What are the major events in programming history that led to the creation of Java?
- 1940s-1950s: Early programming languages like Assembly and Fortran were developed.
- 1960s: High-level languages like COBOL and BASIC were introduced, making programming more accessible.
- 1970s: C language was created, providing low-level access to memory and system resources.
- 1980s: Object-oriented programming (OOP) concepts gained popularity with languages like Smalltalk and C++.
- Early 1990s: The rise of the internet and the need for platform-independent applications.
- 1991: James Gosling and his team at Sun Microsystems started developing a new language called Oak, later renamed Java.
- 1995: Java was officially released, emphasizing platform independence, security, and simplicity.
- Java's "write once, run anywhere" (WORA) philosophy made it popular for web applications and enterprise software.
- 2000s: Java became a dominant language for enterprise applications, mobile development (Android), and big data (Hadoop).
- 2010s: Java continued to evolve with new features and improvements, maintaining its relevance in modern software development.
- Today: Java remains one of the most widely used programming languages, with a large ecosystem and community.

### JDK vs JVM vs JRE
- JDK (Java Development Kit): A software development kit that includes tools for developing, debugging, and monitoring Java applications. It contains the JRE and development tools like the Java compiler (javac), debugger (jdb), and other utilities.
- JRE (Java Runtime Environment): A package that provides the necessary libraries and components to run Java applications. It includes the JVM, core libraries, and other resources needed for execution but does not include development tools.
- JVM (Java Virtual Machine): An abstract computing machine that enables a computer to run Java bytecode. It interprets the bytecode and translates it into machine code specific to the underlying operating system and hardware architecture. The JVM is platform-dependent, meaning there are different implementations for different operating systems (e.g., Windows JVM, Linux JVM, MacOS JVM).
- In summary:
  - JDK = JRE + Development Tools
  - JRE = JVM + Core Libraries
  - JVM = Bytecode Interpreter + Platform-Specific Implementation
- JDK is used by developers to create Java applications, while JRE is used by end-users to run Java applications. The JVM is the core component that executes Java bytecode on a specific platform.

#### Comparison   
| Component | Purpose                          | Includes                                                | Usage                                        |
|-----------|----------------------------------|---------------------------------------------------------|----------------------------------------------|
| JDK       | Development of Java applications | JRE + Development Tools                                 | Used by developers                           |
| JRE       | Running Java applications        | JVM + Core Libraries                                    | Used by end-users                            |
| JVM       | Execution of Java bytecode       | Bytecode Interpreter + Platform-Specific Implementation | Core component for running Java applications |

### Static vs Dynamic Programming Languages
- Static Programming Languages:
  - Type checking is done at compile-time.
  - Variables must be declared with a specific type before use.
  - Examples: Java, C, C++, Swift, Rust.
  - Advantages: Early error detection, better performance due to type optimizations, improved code readability.
  - Disadvantages: Less flexibility, more boilerplate code, longer development time.
- Dynamic Programming Languages:
  - Type checking is done at runtime.
  - Variables can hold values of any type and can change types during execution.
  - Examples: Python, JavaScript, Ruby, PHP, Perl.
  - Advantages: Greater flexibility, faster development time, less boilerplate code.
  - Disadvantages: Runtime errors due to type issues, potentially slower performance, harder to read and maintain code.
- Java is a statically typed language, meaning that variable types are checked at compile-time. This allows for early error detection and optimizations, but requires more boilerplate code and can lead to longer development times.
- Python and JavaScript are dynamically typed languages, allowing for greater flexibility and faster development times. However, this can lead to runtime errors and potentially slower performance due to type checking at runtime.
- C and C++ are statically typed languages, similar to Java, with type checking done at compile-time.

#### Comparison
| Feature              | Static Programming Languages | Dynamic Programming Languages       |
|----------------------|------------------------------|-------------------------------------|
| Type Checking        | Compile-time                 | Runtime                             |
| Variable Declaration | Required                     | Not Required                        |
| Flexibility          | Less Flexible                | More Flexible                       |
| Development Speed    | Slower                       | Faster                              |
| Error Detection      | Early (Compile-time)         | Late (Runtime)                      |
| Performance          | Generally Faster             | Generally Slower                    | 
| Code Readability     | Improved                     | Can be Harder                       |
| Code Safety          | More Type-safe               | Less Type-safe                      |
| Examples             | Java, C, C++, Swift, Rust    | Python, JavaScript, Ruby, PHP, Perl |

#### Compile-time vs Runtime
- Compile-time: The phase when source code is translated into machine code or bytecode by a compiler. Errors related to syntax, type checking, and other static analysis are detected during this phase.
- Runtime: The phase when the compiled code is executed by the computer. Errors related to logic, memory access, and other dynamic behaviors are detected during this phase.
- In statically typed languages like Java, many errors are caught at compile-time, while in dynamically typed languages like Python, more errors may occur at runtime due to the lack of type checking during compilation.

### JVM is reused across different programming languages & advantages
- JVM (Java Virtual Machine) is a platform that can run bytecode generated by various programming languages, not just Java.
- Languages that can compile to JVM bytecode include:
  - Kotlin: A modern, statically typed language fully interoperable with Java.
  - Scala: A functional and object-oriented language that runs on the JVM.
  - Groovy: A dynamic language with features similar to Python and Ruby, also runs on the JVM.
  
#### Advantages of Reusing JVM
| Advantage                | Description                                                                                                                       |
|--------------------------|-----------------------------------------------------------------------------------------------------------------------------------|
| Platform Independence    | JVM allows code written in different languages to run on any platform with a compatible JVM.                                      |
| Java Interoperability    | Can you existing Java libraries.                                                                                                  |
| Performance Optimization | JVM provides Just-In-Time (JIT) compilation speeds up execution and other optimizations that benefit all languages running on it. |
| Rich Ecosystem           | Access to a vast array of libraries and frameworks developed for the JVM, regardless of the language used.                        |
| Mature Tooling           | Benefit from established tools for debugging, profiling, and monitoring JVM applications.                                         |
| Security                 | JVM includes built-in security features like the sandbox model, which can be leveraged by all languages running on it.            |
| Memory Management        | Automatic memory management and garbage collection provided by the JVM.                                                           |
| Community Support        | A large and active community around the JVM ecosystem, providing resources and support for multiple languages.                    |

- Reusing the JVM allows developers to choose the best language for their specific use case while still benefiting from the strengths of the JVM platform.
- This flexibility can lead to increased productivity, better performance, and access to a wider range of tools and libraries.


### What is CLASSPATH?
- CLASSPATH is an environment variable or command-line option that specifies the locations (directories or JAR files) where the Java Runtime Environment (JRE) and Java compiler (javac) look for class files and resources.
- It tells the JVM and Java compiler where to find user-defined classes and packages when running or compiling Java programs.
- If CLASSPATH is not set, the JVM and javac will look for classes in the current directory by default.
- You can set the CLASSPATH using the `-cp` or `-classpath` option when running the `java` or `javac` commands, or by setting the CLASSPATH environment variable in your operating system.
- Example of setting CLASSPATH using the command line:
  - On Windows:
    ```cmd
    set CLASSPATH=C:\myproject\lib\myjar.jar;C:\myproject\classes
    ```
  - On Linux/Mac:
    ```bash
    export CLASSPATH=/myproject/lib/myjar.jar:/myproject/classes
    ```
- Example of using the `-cp` option:
  ```bash
  java -cp /myproject/lib/myjar.jar:/myproject/classes com.example.MyClass
  ```
- java vs javac:
  - `java`: The command used to run Java applications. It uses the CLASSPATH to locate the compiled class files and any additional libraries or resources needed for execution.
  - `javac`: The command used to compile Java source code into bytecode. It uses the CLASSPATH to find any referenced classes or packages that are not part of the standard Java library during compilation.
- You can include multiple paths in the CLASSPATH, separated by a semicolon (;) on Windows or a colon (:) on Linux/Mac.
- You can also use wildcards to include all JAR files in a directory:
  - On Windows:
    ```cmd
    set CLASSPATH=C:\myproject\lib\*
    ```
  - On Linux/Mac:
    ```bash
    export CLASSPATH=/myproject/lib/*
    ```
- Properly setting the CLASSPATH is essential for Java applications to locate and load the necessary classes and resources at runtime.
- In summary, CLASSPATH is a crucial configuration that helps the JVM and Java compiler find the classes and resources needed to run and compile Java programs.
- CLASSPATH is used by both the Java compiler (javac) and the Java Runtime Environment (JRE) to locate class files and resources.
- When you compile a Java program using javac, it uses the CLASSPATH to find any referenced classes or packages that are not part of the standard Java library.
- When you run a Java program using the java command, the JRE uses the CLASSPATH to locate the compiled class files and any additional libraries or resources needed for execution.
- If the CLASSPATH is not set or does not include the necessary paths, you may encounter `ClassNotFoundException` or `NoClassDefFoundError` errors when trying to compile or run your Java programs.
- To avoid such issues, ensure that the CLASSPATH is correctly configured to include all required directories and JAR files.
- You can set the CLASSPATH in your operating system's environment variables or specify it directly when running the java or javac commands using the `-cp` or `-classpath` options.
- In intellij IDEA, when you create a new Java project, the IDE automatically sets up the CLASSPATH for you based on the project's structure and dependencies.
- You can view and modify the CLASSPATH settings in the project structure or module settings within the IDE.
- IntelliJ IDEA also provides features like Maven or Gradle integration, which can manage dependencies and automatically update the CLASSPATH based on the project's build configuration.
- This makes it easier to manage and maintain the CLASSPATH for your Java projects without manually setting it each time.
- In summary, CLASSPATH is a crucial configuration that helps the JVM and Java compiler find the classes and resources needed to run and compile Java programs. Properly setting and managing the CLASSPATH is essential for the successful execution of Java applications.

### ClassLoader in Java
- ClassLoader is a part of the Java Runtime Environment (JRE) that is responsible for loading Java classes into memory during runtime.
- It is a subsystem of the JVM that dynamically loads classes when they are needed, rather than loading all classes at once during the startup of the application.
  - Efficient memory usage: Load classes only when needed. Saving memory.
  - Security: Prevents unauthorized access by controlling class loading.
  - Support for custom class loading: Developers can create their own ClassLoaders to load classes from non-standard sources (e.g., databases, network locations, encrypted files).
- ClassLoaders follow a hierarchical delegation model, where each ClassLoader has a parent ClassLoader. When a ClassLoader is asked to load a class, it first delegates the request to its parent ClassLoader. If the parent ClassLoader cannot find the class, the child ClassLoader attempts to load it.
- Java class files (bytecode) need to be loaded into memory so the JVM can compile them into machine code and execute them.
- Loading Java class files into memory using the ClassLoader happens at runtime, not at compile-time. Compilation of Java source code to bytecode is done by the Java compiler (javac) before the program is run. And classes are loaded into memory when the application is executed.
- There are three main types of ClassLoaders in Java:
  - Bootstrap ClassLoader: The parent of all ClassLoaders, responsible for loading core Java classes from the Java Runtime Environment (JRE) such as `java.lang`, `java.util`, etc. It is implemented in native code and is part of the JVM.
  - Extension ClassLoader: Loads classes from the JRE's extension directories (e.g., `lib/ext`). It is a child of the Bootstrap ClassLoader.
  - System/Application ClassLoader: Loads classes from the application's classpath (e.g., directories and JAR files specified in the CLASSPATH environment variable).
- You can also create custom ClassLoaders by extending the `ClassLoader` class. Custom ClassLoaders can be used to load classes from non-standard sources, such as databases, network locations, or encrypted files.
- ClassLoaders are essential for Java's dynamic loading capabilities, allowing applications to load classes on demand, support plugins, and enable features like hot-swapping of classes during development.
- In summary, ClassLoader is a crucial component of the Java Runtime Environment that dynamically loads Java classes into memory during runtime, following a hierarchical delegation model. It enables Java's platform independence and dynamic loading capabilities.
