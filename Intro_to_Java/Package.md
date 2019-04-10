# Package

* Package: A group of related types, providing access protection and name space management.
  * Type refers to class, interface, enums and annotations.
  
## Why use Packages?
* Easy to determine related types.
* Know where to find types that provide graphic related functions
* Prevent nming conflicts with type names in other packaged because a package creates a new namespace
* Control access

## Creating a Package

~~~
package media
~~~

* `package` keyword 
* Same package name at the top of every source file that you want to include in a package.
* First line of every source file.
* Each source file can have one package.
* If you do not use the package statement, the type ends in an unamed package
  - Only suitable for small/temporary applciations.

## Naming a Package

* Java allows classes to have the same name as long as in different packages.
* The full quialified name of an Item class in media package 
media.Item
* This works fine until two independent programmers use the same name for their package

## Naming Convention

* Package names written in lower case
 * prevents conflict with names of classes or interfaces
* Comapnies use reversed internet domain names to begin their package names e.g. com.infosys.mypackage 
* Packages in the Java language itself begin with java or javax.

## Illegal Package Names
* Begin with a number
* Contains hyphen, special character, reserved word e.g. int
* Use underscore to alleviate this issue

|Domain Name|Package Name Prefix|
|-|-|
|hyphenated-name.org|org.hyphenated_name|
|example.int|int_.example|
|123.example.com|com.example._123name|

# Using Package Memebers

* To use a oublic package memeber from outside its package, do one of the following:

1. **Refer to the member by its full qualified name**

~~~
media.Item m = new media.Item(); 

uk.co.media.Item m;

~~~

* Use this method if the member is to be used inferquently 

2. **Import a Package**

* Import statment at the beginin





