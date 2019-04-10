# First Programs

Programing in Java involves:

1) Defining a class: Fields and Methods.
2) Using a class template to create one or more instances of that class (Object).

## Creating a Class
~~~
public class HelloWorld{
  public static void main (String [] args){
    System.out.println("Hello World");
  }
}
~~~
### Key words explained:
* **class**- Indicates that we are defining a class (HelloWorld is the name of the class). 
* **main** - `main` is the name of the method. The main method indicates start point for the flow of execution.
* **void** - void is the return type. Void indicates that nothing is returned by this method.
* **static** - Static methods belong to the class rather than any instance (object) of the class. <br>
  * Static methods can be invoked without creating an instance of the class (*Classname.methodName*). e.g. Math.sqrt()
  * Static methods can access static data and change its value directly. 
* **String [] arg** - An array of strings called arg, that holds command line arguments.
* System.out.println() - Calls the method println for the class System. println prints the argument provided to it to the console.

~~~
public class PrintArguments{
  public static void main (String [] args){
    System.out.println(args [0])
  }
}
~~~
~~~
$ java PrintArguments Hello World
Hello
~~~
## Creating a field 

* A field stores values for an object.
* Known as instance variables.
* Define the state of an object.
* Have an associated type.
e.g.
~~~
public class Ticket{
  private int price;
  public String destination = "London";
}
~~~
* Java is strongly typed, this means every variable must be declared with a type. 
* `int` is the type given to the field named `price`.
* `String` is the type given to the field names `destination`. We have also given a value to this field (`London`).
* `private` & `public` are access modifiers and define how we can access these fields.

## Creating a Method

* A method is a collection of statements that are grouped together to perform an operation.
* Method signature: 
  - Combination of method name and parameters which can uniquely identify a method. <br>
  - Short description of what a  method does.
  - e.g. public void changePrice(int newPrice){}

* Parameter: A variable that is passed to a method. 
  - public Ticket (int cost) {} // Formal parameter
  - Ticket tm =  new Ticket (10); // Actual parameter (argument) 

* Methods have a return type that tell us what type of data is returned.
  - public int increment() {} // int is the return type

### Types of Methods

#### Constructors

* Create and initate an objects 
* Assign necessary memory to the creates object
* Same name as class
* Typically store inital values into fields
  - Often from external arguments
* No return type
* e.g.
~~~
public Ticket (int cost){
  price = cost;
}
~~~

#### Accessor Methods
* *getter* 
* provide information about an object's state
* e.g.
~~~
public int getPrice(){
  return price;
}
~~~

#### Mutator Methods
* *setters*
* change (mutate) an object's state
* e.g.
~~~
public void changePrice (int newPrice){
  price = newPrice;
}
~~~

## Class Conventions

* Class names are written in PascalCase e.g public class TicketMachine{}
* Method names are written in camelCase e.g public void printTicket(){}
* Field names are written in camelCase e.g. public int ticketPrice;
* Constants are written in ALL_CAPS with an underscore separating words e.g. 
public static final String TICKET_ERROR_101="Train has already departed";
* Constructors are (almost) always public
* No direct access to fields (mark fields as private and access via accessors and mutators);
* User does not need to know how a class is implemented to use/insantiate it.
* Use of class is defined by its collection of methods

## Comments
~~~
// This is an inline comment 
/*
* This is a
* block comment 
*/
~~~
* Java ignores comments.
~~~
public class Ticket{
  
  //field
  private int ticketPrice; 
  
  //Constructor method, has same name as class (note captilalization), no return type (not even void)!  
  public Ticket (int price){ 
    ticketPrice=price;
  }
  
  //Mutator method
  public void changePrice(int newPrice){
    ticketPrice=newPrice;
  }
  
  //Accessor method
  public int getPrice(){
    return ticketPrice;
  }    
}
~~~

## Instantiating a Class

* Now that a class has been made it must be instantiated so that the fields and methods of the class can be used.

~~~
public class TicketMachine{
  public static void main (String [] args){
    Ticket tm = new Ticket (10);
    tm.changePrice(20);
    System.out.println(tm.getPrice());
  }
}
~~~
~~~
$ javac Ticket.java TicketMachine.java
$ java TicketMachine.java

20
~~~
~~~
  (1)  (2)   (3)  (4) (5)
Ticket tm = new Ticket(10);

1. Declaration of the Object type.
2. Name of the object.
3. Instantiation by using the new key word to create an object.
4. Initialization by calling the constructor of the object. Note if no constructor is explicity defined then an empty default constructor is created.
5. The value 10 is passed to the constructor as an argument. 
~~~
* A user does not need to know how a class is implemented to use it.
* The use of a class is defined by its collection of methods.
