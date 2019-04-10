# Java as a Platform

* Java is a platform because it is a piece of software that excecutes a program. 
* Java has 3 main software components: Java Development Kit, Java Runtime Environment and Java Virtual Machine, each with a different configuation for a specific operating system.

## JVM

* JVM (Java Virtual Machine) is an abstract machine.
* 'Virtual' because it doesn't physically exist.
* In reality JVM is a specification.
* The JVM specification details what is requried of a JVM implementation to provide a runtime environment to excecute Java bytecode.

### Implementation of JVM
* Implementations of JVM are known as Java Runtime Environments (JREs).
* JREs for a given platform can excecute any compiled java program on the given platform.
* Implementations of the JRE are provided by Oracle as well as other companies.
* JREs can also run programs written in other languages...provided they are first compiled to Java bytecode.

### More on the JVM Specification

* JVM specification provides definitions for the:
  - Memory area.
  - Class file format.
  - Register set.
  - Garbage-collected heap.
  - Fatal error reporting etc.

### What does the JVM do?

1) Loads code.
2) Verifies code.
3) Exceutes code.
4) Provides runtime environment. 

### JVM Archtiecture 
![JVM Architecture](https://github.com/RyanLPrince/Java-Reference-Guide/blob/master/Intro_to_Java/Resources/Images/JVM_Architecture.png)

1) Classloader <br>
* Loads class files.
* Whenever a java program is run, it is first loaded by the classloader. 
* There are three built-in classloaders in Java.
  - Bootstrap ClassLoader: 
      - Loads rt.jar file.
        - rt.jar contains all class files of the Java SE e.g. java.lang, java.util packages (compiled java runtime libraries). 
      - Loads other core libraries located in $JAVA_HOME/jre/lib directory
  - Extension Classloader: 
    - Child of Bootstrap.
    - Loads the jar files located inside $JAVA_HOME/jre/lib/ext directory.
      - so that these extensions of the core java libraries are available to all applications running on the platform.
  - System/Application ClassLoader: 
    - Child of extension classloader
    - Loads application level classes into the JVM. 
    - It loads files found in the classpath environment variable
~~~
String.class.getClassLoader()   //null because String class is part of rt.jar and hence loaded by native Bootstrap classloader
MyClass.class.getClassLoader()  // sun.misc.Launcher$AppClassLoader@4e0e2f2a 
~~~
2) Class Area <br>
* Class Area (Method) stores class structures such as:
  - Runtime constant. 
  - Field and method data.
  - Code for methods.
  - (Stores class)

3) Heap <br>
* Runtime data area.  
* Memory for all class instances and arrays are allocated.
* (Stores instance of a class)

4) Stack <br>
* JVM creates a separate stack each time a thread is created.
* Each method call performed by the thread and corresponding local variables will be stored in the stack.
* For every method call a separate 'frame' will be added to the stack.
* Frames store local variables, partial results, and plays a part in method invocation and return. 
* After completing the method call the corresponding frame will be removed from the stack.
* After all the method calls are complete the stack will become empty and the empty stack will be destroyed by the JVM.

5) Program Counter Register <br>
* PC (program counter) register contains the address of the Java virtual machine instruction currently being executed.

6) Native Method Stack <br>
* It contains all the native methods used in the application.
* A native method is a Java method whose implementation is written in another programming language such as C. 
  - Write faster code on a critical section with better CPU assembly instructions (not CPU portable).
  - Make direct system calls (not OS portable).

7) Execution Engine <br>
* It contains:
  - A virtual processor
  - Interpreter: Read bytecode stream then execute the instructions.
  - Just-In-Time(JIT) compiler: It is used to improve the performance. JIT compiles parts of the byte code that have similar functionality at the same time, and hence reduces the amount of time needed for compilation. Here, the term "compiler" refers to a translator from the instruction set of a Java virtual machine (JVM) to the instruction set of a specific CPU.
  
8) Java Native Interface <br>
* Java Native Interface (JNI) is a framework which provides an interface to communicate with another application written in another language like C, C++, Assembly etc. 
* Java uses JNI framework to send output to the Console or interact with OS libraries.

## JRE

* JRE (Java Runtime Environment) is the implementation of JVM.
* Set of software tools which are used for developing Java applications.
* Provides runtime environment.
* Set of libraries & other files JVM uses at runtime. 
* Actively released by Oracle as well as other companies.

![JRE](https://github.com/RyanLPrince/Java-Reference-Guide/blob/master/Intro_to_Java/Resources/Images/JRE.png)

## JDK

* JDK (Java Development Kit)
* Software development environment which is used to develop Java applications and applets. 
* Contains JRE + development tools.
* JDK is an implementation of any of the below released by Oracle Corporation:
  - Standard Edition Java Platform
  - Enterprise Edition Java Platform
  - Micro Edition Java Platform
* JDK contains a private JVM and other resources to complete the development of a java Application e.g.:
  - Interpreter (java).
  - Compiler (javac).
  - Archiver (jar).
  - Document generator (javadoc).
  
![JDK](https://github.com/RyanLPrince/Java-Reference-Guide/blob/master/Intro_to_Java/Resources/Images/JDK.png)

The JRE contains everything necessary to run an **already compiled Java program**, including the Java Virtual Machine (JVM) and other infrastructure. However, it cannot be used to create new programs. The JDK contains everything the JRE has, but also the compiler (javac) and other tools required for creating and compiling new programs.
