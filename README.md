# HashSetInternalWorking

# A Java HashSet represents a set of elements (objects). It does not guarantee the order of insertion elements.It contains unique elements.

# It uses a technique to store elements based on hashcode

# HashSet internally uses HashMap internally in java

# When we create an object of HashSet, it internally creates an instance of HashMap with default initial capacity 16.

# HashSet can be created using 4 HashSet constructors

# The initial default capacity of HashSet is 16. The default load factor is 0.75.

# Set internal code is below

public class HashSet<E> extends AbstractSet<E>  
{  
private transient HashMap<E,Object> map;  
// Dummy value to associate with an Object in the backing Map  
private static final Object PRESENT = new Object();  
public HashSet()  
{  
map = new HashMap<>();  
}  
public boolean add(E e)   
{  
return map.put(e, PRESENT)==null;  
  //If the Key (e) is unique and added to the map, then it will return null
  //If the Key (e) is duplicate, then it will return the old value of the key.
}  
} 
  In the above code a call to add(object) is delegated to put(key, value) internally. Where key is the object we have passed and the value is another object, called PRESENT. It is a constant in java.util.HashSet.
  We are maintaing uniqueness of objects in HashSet using HashMap internally 
