## SOLID Principles
Stands for:
- **S**ingle Responsibility Principle (SRP), 
- **O**pen closed Principle (OSP), 
- **L**iskov substitution Principle (LSP), 
- **I**nterface Segregation Principle (ISP), and 
- **D**ependency Inversion Principle (DIP).

### Single Responsibility Principle (SRP) 
"Every software module should have only one reason to change".

### Open closed Principle (OSP)
"A software module/class is open for extension and closed for modification".
- open for extensions => inheritance 
- closed for modification => means we have already developed a class and it has gone through testing. We should then not alter it until we find bugs. 

Example:
```
Abstract class Shape with abstract method Area()
Class Rectangle and Circle Inherits from Shape
AreaCalculator class receives Shape and calculates the TotalArea()
```

### Liskov Substitution Principle (LSP) 
"You should be able to use any derived class instead of a parent class and have it behave in the same manner without modification".
- Extension of the Open Closed Principle

Example:
```
SqlFile class and SqlFileManager class
Added ReadOnlySqlFile class inheriting from SqlFile - Problem on writing method 
Solution: IReadableSqlFile with LoadText() and IWritableSqlFile with SaveText()
ReadOnlySqlFile: IReadableSqlFile
SqlFile: IWritableSqlFile,IReadableSqlFile
```

### Interface Segregation Principle (ISP)
- That clients should not be forced to implement interfaces they don't use. Instead of one fat interface, many small interfaces are preferred based on groups of methods, each one serving one submodule.
- An interface should be more closely related to the code that uses it than code that implements it.

### Dependency Inversion Principle (DIP)
"High-level modules/classes should not depend on low-level modules/classes. Both should depend upon abstractions. Secondly, abstractions should not depend upon details. Details should depend upon abstractions".
- High-level modules/classes implement business rules or logic in a system (application). 
- Low-level modules/classes deal with more detailed operations; in other words they may deal with writing information to databases or passing messages to the operating system or services.



References
https://www.c-sharpcorner.com/UploadFile/damubetha/solid-principles-in-C-Sharp/
