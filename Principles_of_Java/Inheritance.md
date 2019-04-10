# Inheritance

* Inheritance is the process where once class accquires methods and fields from another.

1. Define superclass
2. Define subclass
3. Superclass defines common attributes
4. subclass inherits superclass attributes
5. subclass adds its own attributes

* `extends` key word.
* Subclass constructors may contain a `super` call to its superclass constructor in the first line in the subclass constructor.
* If no constructor is written, the compiler inserts a default constructor. 

* Every class inherits from the Object super class

## Advantages

* Avoid code duplication.
* Allow code reuse.
* SImplifies code.
* Simplifies maintenance and extension.

## Method Lookup/Dispatch

1. Subclass is searched for a method match.
2. If no match is found superclass is searched.
3. Repeated until a match is found or class hierachy is exhausted.


## Overiding

* When a subclass implements a parent class method based on its requirements
* Can call overriden methof by using super key word. e.g. super.methodName, super.variableName.

* Classes can only inherit from a single class (No multiple inheritance).
  * This avoids competing definitions of methods and fields.
