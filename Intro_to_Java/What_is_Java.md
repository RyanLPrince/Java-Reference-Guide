# What is Java?

* Java is a **programming language** and a **platform** .

**Platform**: Any hardware or software environment in which a program runs, is known as a platform. <br> 
Since Java has a runtime environment (JRE) and API, it is refered to as a platform.

## Types of Java Application

1) Standalone Application <br>
'Desktop applications'. Traditional software that needs to be installed on each client system. Access to the application is limited to the systems that have the application installed. Standalone applications can be adventageous when there is no need for networking (application is needed only on a single system) or for hardware support such as barcode printers, webcams, biometric devices, LED Panels, etc.

2) Web Application <br>
Web applications are distributed by nature, meaning that they are programs that run on more than one computer and communicate through a network or server. Usually, web applications are accessed via a web browser because of the ease of using the browser as a user client. Web applicaitions are advantageous because they offer the ability to update and maintain the application without deploying and installing software on every client e.g. e-mail, online retail sales, discussion boards, online banking etc. 

A web server is a software that can process the client request and send the response back to the client. For example, Apache is one of the most widely used web server. Web servers runs on some physical machine and listens to client requests on specific port.

A web client is a software that helps in communicating with the server. Some of the most widely used web clients are Firefox, Google Chrome, Safari etc. When we request something from server (through URL), web client takes care of creating a request and sending it to server and then parsing the server response and present it to the user.

An application that **runs on the server side** and creates a **dynamic page** is called a web application. <br>
Currently, Servlet, JSP, Struts, Spring, Hibernate, JSF, etc. are technologies used for creating web applications in Java.

3) Enterprise Application <br>
An application that is **distributed** in nature, such as a banking application. <br> 
It has advantages of the **high-level security**, **load balancing** and **clustering**. <br>
In Java, EJB are used for creating enterprise applications.

4) Mobile Application <br>
Currently, Android and Java ME are used for creating mobile applications.

## Java Platforms / Editions

1) Java SE (Java Standard Edition) <br>
Java SE is a programming platform. It includes Java programming APIs such as java.lang, java.io, java.net, java.util, java.sql, java.math etc. It includes core topics like OOPs, String, Regex, Exception, Inner classes, Multithreading, I/O Stream, Networking, AWT, Swing, Reflection, Collection, etc.

2) Java EE (Java Enterprise Edition) <br>
An enterprise platform which is mainly used to develop web and enterprise applications. It is built on the top of the Java SE platform. It includes topics like Servlet, JSP, Web Services, EJB, JPA, etc.

3) Java ME (Java Micro Edition) <br>
It is a micro platform which is mainly used to develop mobile applications.

4) JavaFX <br>
It is used to develop rich internet applications. It uses a light-weight user interface API.

## Features of Java:

1) **Simple**<br>
* Syntax based on C++.
* Removed complicated features e.g. explicit pointers, operator overloading.
* Automatic garbage collection of unreferenced objects.
2) **Object - Oriented**<br> 
* Promotes code and object reuse. 
* Focus on higher level of programming, functionality over implementation.
* Simplifies design for larger projects.
3) **Portable** <br>
* Platform independent can be run on multiple different platforms and operating systems once compiled. 
4) **Secure** <br>
* No explicit pointer.
* Java Programs run inside a virtual machine sandbox (JVM).
* Classloader: Classloader in Java is a part of the Java Runtime Environment(JRE) which is used to load Java classes into the Java Virtual Machine dynamically. It adds security by separating the package for the classes of the local file system from those that are imported from network sources.
* Bytecode Verifier: It checks the code fragments for illegal code that can violate access rights to objects.
* Security Manager: It determines what resources a class can access such as reading and writing to the local disk.
5) **Robust**
* It uses strong memory management.
* Lack of pointers avoids security problems.
* Automatic garbage collection  runs on the Java Virtual Machine to get rid of objects which are not being used by a Java application anymore.
* Exception handling and the type checking mechanism.
6) **Architecture neutral** <br>
* No implementation dependent features, e.g. the size of primitive types are fixed.
  - Compare with C : int data type occupies 2 bytes of memory for 32-bit architecture and 4 bytes of memory for 64-bit architecture.
  - In Java int occupies 4 bytes of memory for both 32 and 64-bit architectures.
7) **Performance** <br>
* Java is faster than other traditional interpreted programming languages because Java bytecode is "close" to native code.
* It is still a little bit slower than a compiled language (e.g., C++). 
* Java is an interpreted language that is why it is slower than compiled languages, e.g., C, C++, etc.
8) **Distributed** <br>
* RMI and EJB are used for creating distributed applications. 
9) **Multithreading** <br>
* A thread is like a separate program, executing concurrently. 
* We can write Java programs that deal with many tasks at once by defining multiple threads. 
* The main advantage of multi-threading is that it doesn't occupy memory for each thread. It shares a common memory area. 
* Threads are important for multi-media, Web applications, etc.
10) **Dynamic** <br>
* Dynamic loading of classes: classes are loaded on demand. 
* Dynamic compilation and automatic memory management (garbage collection).

