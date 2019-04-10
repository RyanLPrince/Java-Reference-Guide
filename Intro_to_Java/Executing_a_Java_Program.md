# Executing a Java Program

* Java is both compiled and interpreted.

~~~
              (Compiler)           (JIT Compiler)
Java Program -----------> Byte Code -------------> Excecuted Program
                                   (or Interpreter)
~~~ 

* Compiler: Transforms statements written in a programming language into another programming langauge (usually low level machine language).

* Interpreter: Directly executes instructions written in a progrmming language (without them being previously compiled into machine language).

* JIT Compiler: Just-In-Time compiler, compiles byte code to machine langauage on the fly at run time. 
It is used to improve the performance. JIT compiles parts of the byte code that have similar functionality at the same time,
and hence reduces the amount of time needed for compilation. Here, the term "compiler" refers to a translator 
from the instruction set of a Java virtual machine (JVM) to the instruction set of a specific CPU.

* A Java virtual machine can either interpret the bytecode one instruction at a time (mapping it to a real processor instruction) 
or the bytecode can be compiled further for the real processor using a just-in-time compiler.

## Compiling and Executing Java Programs

* The java file name should be the same as the class name (if public) with the `.java` extension. 

###### HelloWorld.java
~~~
public class HelloWorld {
  public static void main (String [] args){
  }
}
~~~
~~~
$ javac HelloWorld.java           ⭠ This creates a HelloWorld.class file, the corresponding Java byte code.
$ javac *.java                    ⭠ Compiles all the java files in the directory

$ java HelloWorld                 ⭠ Excecutes HelloWorld.class files. This command is used on the class with the main method. 
~~~

* If your java class is not public the file name does not have to match the class name. 
e.g. we could save the following file as RandomName.java.

~~~
class GoodbyeWorld {
  public static void main (String [] args){
  }
}
~~~

~~~
$ javac RandomName.java           ⭠ This creates a GoodByeWorld.class file, the corresponding Java byte code.


$ java GoodbyeWorld               ⭠ Excecutes GoodbyeWorld.class files. This command is used on the class with the main method. 
~~~
