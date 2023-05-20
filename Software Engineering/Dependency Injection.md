A class accepts the objects it requires from an injector instead of creating the objects directly. A class should concentrate on fulfilling its responsibilities not on objects that are required to fulfill them and those objects are provided by dependency injection.

There are different types of DI; By constructor, by setter and by field. DI by constructor is done by passing the objects required through the class constructor. 
DI by setter is to create an instance and then add the dependency via the setter to the dependent class.
DI by field is done by assigning dependency to the attribute of the dependent class directly which is not recommended because of [encapsulation]([[OOP Principles#Encapsulation]]).


#### Reference
[Geekific-YouTube](https://www.youtube.com/watch?v=GATSXm7WAxU)
