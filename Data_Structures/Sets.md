# Sets

* A Set is a Collection that cannot contain duplicate elements.
* The Set interface contains only methods inherited from Collection and adds the restriction that duplicate elements are prohibited.
* Set also adds a stronger contract on the behavior of the equals and hashCode operations, allowing Set instances to be compared meaningfully even if their implementation types differ.
* Two Set instances are equal if they contain the same elements.

## Set Implementations

* The Java platform contains three general-purpose Set implementations:
  - HashSet
  - TreeSet
  - LinkedHashSet
  
### HashSet
* Stores its elements in a hash table.
* Best performance.
* No guarantees concerning order of iteration.

## TreeSet
* Stores its elements in a red-black tree.
* Orders its elements based on their values.
* Substantially slower than HashSet. 

## LinkedHashSet
* which is implemented as a hash table with a linked list running through it.
* Orders its elements based on the order in which they were inserted into the set (insertion-order). 
* LinkedHashSet no chaotic ordering unlike HashSet.

## Examples Use Case

You have a Collection, c, and you want to create another Collection containing the same elements but with all duplicates eliminated. The following one-liner does the trick.
~~~
Collection<Type> noDups = new HashSet<Type>(c);
~~~

~~~
Collection<Integer> c = new ArrayList<>();
c.add(1); c.add(1);
System.out.println(c); // [1,1]
c = new HashSet<Integer>(c); // Conversion constructor
System.out.println(c); // [1]
~~~
* Or using aggregate operations
~~~
c.stream()
.collect(Collectors.toSet()); // no duplicates
~~~
* Here's a slightly longer example that accumulates a Collection of names into a TreeSet:
~~~
Set<String> set = people.stream()
.map(Person::getName)
.collect(Collectors.toCollection(TreeSet::new));
~~~

Preserve the order of the original collection while removing duplicate elements:
~~~
Collection<Type> noDups = new LinkedHashSet<Type>(c);
~~~
* The following is a generic method that encapsulates the preceding idiom, returning a Set of the same generic type as the one passed.
~~~
public static <E> Set<E> removeDups(Collection<E> c) {
    return new LinkedHashSet<E>(c);
}
~~~
