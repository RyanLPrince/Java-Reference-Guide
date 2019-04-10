# Access Modifiers, Static and Final 

## Access Modifiers 

* Define levels of access for classes, fields and methods. 
* **Class**
  - public: visible to all classes everywhere 
  - No modifier: visible within own package
  
 * **Methods & Fields**
  - public: visbile to all classes everywhere, can change field without a 'setter' method, can invoke method on object within a differnt class. 
  - No modifier: visible within own package
  - private: Accessed by own class, can change field with a 'setter' method, cannot invoke method on object within a differnt class. private methods are only used internally by class within which it is written. 
  - protected: Visbile within package and subclasses in other packages.
  
  |Modifier   |Class|Package|Sublass|World|
  |-          |-    |-      |-      |-    |
  |public     |Y    |Y      |Y      |Y    |
  |protected  |Y    |N      |Y      |N    |
  |no modifier|Y    |Y      |N      |N    |
  |private    |Y    |N      |N      |N    |
  
* If you make any class constructor private, you cannot create the instance of that class from outside the class.

# Static 

* **Variable:**
  - Associated with class rather than any object (instance).
  - If variable is changed, the change is replicated for all instances.
  - Can be accessed directly by class name with no object required.
* **Methods:**
  - Can be invoked without creating an object.
  - Belongs to class rather than object of a class.
  - static methods can only modify static fields directly.
  - static methods can modify non-static fields with an object reference. 
  - 'this' and 'super' cannot be used in a static context. 
* **Classes:**
  - Only when nested within non-static classes
  - static class acts like separate class but can access static members of class that enclose it.
  
# Final

* **Variable:**
  - When a variable is declared with final keyword, its value can’t reassigned.
  - A static final finals variable is a constants.
  - Must initialize a final variable.
  - If the final variable is a reference, this means that the variable cannot be re-bound to reference another object, but internal state of the object pointed by that reference variable can be changed
  - E.g. you can add or remove elements from final array or final collection.
  - It is good practice to represent final variables in all uppercase, using underscore to separate words.
 
* **Methods:**
  - Cannot be overidden.  
  
* **Class:**
  - Cannot be extended. 
