`dataclass` module is a utility tool to make structured classes specially for storing data. These classes hold certain properties and functions to deal specifically with the data and its representation.

There are two noticeable points about dataclasses.   
- Without a [__init__()](https://www.geeksforgeeks.org/constructors-in-python/) constructor, the class accepted values and assigned it to appropriate variables.
- The output of printing object is a neat representation of the data present in it, without any explicit function coded to do this. That means it has a modified [__repr__()](https://www.geeksforgeeks.org/object-oriented-programming-in-python-set-2-data-hiding-and-object-printing/) function.

The `dataclass` provides an in built __init__() constructor to classes which handle the data and object creation for them.

**Equality of Data Classes**   
Since the classes store data, checking two objects if they have the same data is a very common task that’s needed with dataclasses. This is accomplished by using the == operator.

Equality between two objects using == operator in python checks for the same memory location. Since two objects take different memory locations on creation, the output for equality is **False**. Equality between DataClass objects checks for the equality of data present in it. This accounts for **True** as output for equality check between two DataClass objects which contain same data.





#### Reference 
[GeeksForGeeks-1](https://www.geeksforgeeks.org/data-classes-in-python-an-introduction/)

