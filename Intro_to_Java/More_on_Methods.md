# More on Methods

## Method Overloading

* When a class has multiple methods with the same name but different parameters (different method signatures).
e.g.
~~~
public int adder (int x, int y){
 return x+y;
}

public int adder (int x, int y, int z){
 return x+y+z;
}

public String adder (String x , String y) {
	try {
		    int num1=Integer.parseInt(x);
    		int num2=Integer.parseInt(y);	
    		return (num1+num2)+"";
	}catch (NumberFormatException e) {
		return e.getMessage();	
	}
}
~~~
~~~
MyClass.adder(1,2);
>>> 3

MyClass.adder(1,2,3);
>>> 6

MyClass.adder("1","2");
>>> 3

MyClass.adder("1","a");
>>> For input string: "a"
~~~
## Varargs

* The example above can be made more efficient by utilising varargs.
* Varargs is short for variable-length arguments.
* It simplifies the creation of methods that take a variable number of arguments.
* Prior to the introduction of varargs variable length arguments were either handled by method overloading or by placing the variables into an array.
* Varargs methods are specified by `...` this tells the compiler that this method can be called with 0 or more arguments.
* Arguments supplied to this method will be declared as an array of the type given in the parameter. 

~~~
public int adder (int ... values){
	int sum=0;
	for (int number: values){
		sum=sum+number;
	 }
 	return sum;
}
~~~
~~~
MyClass.adder(1,2)
>>> 3

MyClass.adder(1,2,3)
>>> 6
~~~
* This method uses a for loop to access each argument supplied to the method. 

## 'this' keyword

* Whithin an instance method or constructor, `this` is a reference to the current object, the object whose method or constructor is being called. 

### Using this with a field

* Most common reason for using 'this' is because a field is shadowed by a method or constructor parameter e.g.

###### Without 'this'

~~~
public class Ticket{
  private int cost;
  public Ticket(int price){
    cost = price;
  }
}
~~~
* The field 'cost' is not shadowed by the parameter 'price'.

###### With 'this' 
~~~
public class Ticket{
  private int cost;
  public Ticket(int cost){
    this.cost = cost;
  }
}
~~~
* The field 'cost' is shadowed by the parameter 'cost'.
~~~
this.cost = cost;
(field)     (parameter)
~~~

* Inside the constructor 'cost' is a local copy of the constructors first argument.
* To refer to the field we must use `this.cost`.
* The this keyword allows us to refer to the field 'cost' which shares the same name as the parameter.

### Using 'this' with a Constructor

* From within a constructor, you can use 'this' to call another constructor in the same class. - Explicit constructor invocation.
~~~
public class Rectangle{
	private int x, y;
	private int width, height;
	
	public Rectangle() {
		this(0, 0, 1, 1);
	}
	
	public Rectangle(int width, int height){
		this (0, 0, width, height);
	}
	
	public Rectangle( int x, int y, int width, int height){
		this.x = x;
		this.y = y;
		this.width = width;
		this.height =height;	
	}
}
~~~

~~~
Rectangle rectangle = new Rectangle (); // (0, 0, 1, 1)
		      new Rectangle (10, 20); // (0, 0, 10, 20)
		      new Rectangle (8, 16, 5, 1); // (8, 16, 5, 1)
~~~

