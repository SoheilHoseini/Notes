#### Single Responsibility
A class has to have only one responsibility and only one reason to change.

#### Open Closed 
A class should be open to extension but closed to modification.

#### Liskov Substitution
Subtypes should be replaceable by their base type (parent class). This means we should be careful using inheritance. For example we have a `Video` class with some methods including one for playing random advertisements `randomAds()`. Now for managing premium videos, we need another class in which has many attributes in common with `Video` called `PremiumVideo`. But since we don't have ad in premium, we have to override `randomAds()` and throw an exception in case it is being used wrongly but this could cause an unpredicted crash in our app. So we should use *composition* instead of *inheritance* and create a `VideoManager` class which contains most of the common behaviors between `Video` and `PremiumVideo` and then instantiate `VideoManager` in each of them and use the methods we see fit.

#### Interface Segregation 
Many specific interfaces is better that a general interface. In the example mentioned above to solve the problem, we can assume we have an interface `IVideos` which contains both ad related and non-related functionalities needed and having `Video` and `PremiumVideo` implement it. But we would face the exception problem again. Instead we could define two more specific interfaces in which one contains ad-related methods and the other containing other methods, and our two classes implementing each of them as they require.

#### Dependency Inversion 
We must depend on abstractions and not concrete classes. High level modules should not depend on low level modules; Both should depend on abstractions.




