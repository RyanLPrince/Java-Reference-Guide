# Collections

* Collections represent a group of objects known as elements.
* The Collection interface is used to pass around collections of objects in a generic manner.
* For example, by convention all general-purpose collection implementations (e.g. ArrayList) have a constructor that takes a Collection argument. 
  - This constructor is known as a conversion constructor.
  - It initializes the new collection to contain all of the elements in the specified collection, whatever the given collection's subinterface or implementation type. 
  - In other words, it allows you to convert the collection's type.
  - `<T>` is a generic and can usually be read as "of type T".
  - Specifying angular brackets after the class name means you are creating a temporary data type which can hold any type of data.
~~~
public ArrayList(Collection<? extends E> c) {
    elementData = c.toArray();
    if ((size = elementData.length) != 0) {
        // c.toArray might (incorrectly) not return Object[] (see 6260652)
        if (elementData.getClass() != Object[].class)
            elementData = Arrays.copyOf(elementData, size, Object[].class);
    } else {
        // replace with empty array.
        this.elementData = EMPTY_ELEMENTDATA;
    }
}
~~~

* Example: you have a Collection<String> c, where c may be a List, a Set, or another kind of Collection. 
* We can create a new ArrayList (an implementation of the List interface), initially containing all the elements in c by doing the following:

~~~
List<String> list = new ArrayList<String>(c);
~~~
OR in JDK 7 or later, using the diamond operator:

~~~
List<String> list = new ArrayList<>(c);
~~~

* The Diamond Operator reduces some of Java's verbosity surrounding generics by having the compiler infer parameter types for constructors of generic classes. 

~~~
Map<String, List<String>> anagrams = new HashMap<String, List<String>>();
~~~
* This is rather lengthy, so it can be replaced with this:
~~~
Map<String, List<String>> anagrams = new HashMap<>();
~~~

## Methods 

* The Collection interface contains methods that perform basic operations, such as int size(), boolean isEmpty(), boolean contains(Object element), boolean add(E element), boolean remove(Object element), and Iterator<E> iterator().

* It also contains methods that operate on entire collections, such as boolean containsAll(Collection<?> c), boolean addAll(Collection<? extends E> c), boolean removeAll(Collection<?> c), boolean retainAll(Collection<?> c), and void clear().

* In JDK 8 and later, the Collection interface also exposes methods Stream<E> stream() and Stream<E> parallelStream(), for obtaining sequential or parallel streams from the underlying collection. 

* The add method is defined generally enough so that it makes sense for collections that allow duplicates as well as those that don't. It guarantees that the Collection will contain the specified element after the call completes, and returns true if the Collection changes as a result of the call. 

~~~
List <Integer> list = new ArrayList<> ();
System.out.println(list.add(1)); //true
System.out.println(list.add(1)); //true
~~~
~~~
Set <Integer> set = new HashSet<> ();
System.out.println(set.add(1)); //true
System.out.println(set.add(1)); //false
~~~
* Similarly, the remove method is designed to remove a single instance of the specified element from the Collection, assuming that it contains the element to start with, and to return true if the Collection was modified as a result.

## Traversing Collections
There are three ways to traverse collections: (1) using aggregate operations (2) with the for-each construct and (3) by using Iterators.

### (1) Aggregate Operations
>In JDK 8 and later, the preferred method of iterating over a collection is to obtain a stream and perform aggregate operations on it. Aggregate operations are often used in conjunction with lambda expressions to make programming more expressive, using less lines of code. 

* The following code sequentially iterates through a collection of shapes and prints out the red objects:
~~~
myShapesCollection.stream()
.filter(e -> e.getColour() == Colour.RED)
.forEach(e -> System.out.println(e.getName()));
~~~
* Likewise, you could easily request a parallel stream, which might make sense if the collection is large enough and your computer has enough cores:
~~~
myShapesCollection.parallelStream()
.filter(e -> e.getColor() == Color.RED)
.forEach(e -> System.out.println(e.getName()));
~~~

* There are many different ways to collect data with this API. 
* For example, you might want to convert the elements of a Collection to String objects, then join them, separated by commas:
~~~
String joined = elements.stream()
  .map(Object::toString)
  .collect(Collectors.joining(", "));
~~~
* Or perhaps sum the salaries of all employees:
~~~
int total = employees.stream()
  .collect(Collectors.summingInt(Employee::getSalary)));
~~~

>The Collections framework has always provided a number of so-called "bulk operations" as part of its API. These include methods that operate on entire collections, such as containsAll, addAll, removeAll, etc. Do not confuse those methods with the aggregate operations that were introduced in JDK 8. The key difference between the new aggregate operations and the existing bulk operations (containsAll, addAll, etc.) is that the old versions are all mutative, meaning that they all modify the underlying collection. In contrast, the new aggregate operations do not modify the underlying collection. When using the new aggregate operations and lambda expressions, you must take care to avoid mutation so as not to introduce problems in the future, should your code be run later from a parallel stream.

### For-each Construct

* The for-each construct allows you to concisely traverse a collection or array using a for loop 
~~~
for (Object o : collection)
    System.out.println(o);
~~~

### Iterators
* An Iterator is an object that enables you to traverse through a collection and to remove elements from the collection selectively, if desired. 
* You get an Iterator for a collection by calling its iterator method. The following is the Iterator interface.
~~~
public interface Iterator<E> {
    boolean hasNext();
    E next();
    void remove(); //optional
}
~~~  
* The hasNext method returns true if the iteration has more elements.
* The next method returns the next element in the iteration. 
* The remove method removes the last element that was returned by next from the underlying Collection.
* The remove method may be called only once per call to next and throws an exception if this rule is violated.

* Note that Iterator.remove is the only safe way to modify a collection during iteration; the behavior is unspecified if the underlying collection is modified in any other way while the iteration is in progress.

### Iterator vs for-each

* Use Iterator instead of the for-each construct when you need to:

* Remove the current element. 
  - The for-each construct hides the iterator, so you cannot call remove.
  - The for-each construct is not usable for filtering.
* Iterate over multiple collections in parallel.

* The following method shows you how to use an Iterator to filter an arbitrary Collection — that is, traverse the collection removing specific elements.

~~~
static void filter(Collection<?> c) {
    for (Iterator<?> it = c.iterator(); it.hasNext(); )
        if (!cond(it.next()))
            it.remove();
}
~~~
* This simple piece of code is polymorphic, which means that it works for any Collection regardless of implementation. 
  - This example demonstrates how easy it is to write a polymorphic algorithm using the Java Collections Framework.


## Collection Interface Array Operations
The toArray methods are provided as a bridge between collections and older APIs that expect arrays on input. The array operations allow the contents of a Collection to be translated into an array. The simple form with no arguments creates a new array of Object. The more complex form allows the caller to provide an array or to choose the runtime type of the output array.

~~~
HashSet<Integer> set = new HashSet();
  set.add(1);set.add(2);
  Object list [] = set.toArray();
~~~
