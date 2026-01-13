referenced from https://fullscale.io/blog/software-engineering-principles/

**1. Keep it simple**
- strive for simplicity in design and implementations
- avoid complexity
- focus on creating clean and readable code

**2. Don't repeat yourself**
- eliminate redundancy
-  promote code reuse and modular design to improve efficiency
- centralize common functionalities and avoid duplication
  
**3. You aren't gonna need it**
- implement features that are currently required
- resist temptation to add unnecessary functionality
- deliver value incrementally
  
**4. Separation of concerns**
- divide software into independent modules/components
- assign each module a responsibility and minimize overlap
- promote loose coupling and high cohesion

 **5. Modularity**
- design software as a collection of interchangeable and reusable modules
- encapsulate related functionalities into one unit
- enable easy modification, testing, and replacement of modules

**6. Single Responsibility Principle (SRP)**
- each module, class, or function should have a single defined responsibility
- avoid mixing multiple concerns into a single unit of code
- facilitate codebase understanding, testing, and maintenance
  
**7. Open-Closed Principle (OCP)**
- software entities should be open for extension but closed for modification
- encourage abstractions and interfaces to enable extensibility
- minimize impact of changes on existing code
                
**8. Liskov Substitution Principle (LSP)**
- subtypes should be substitutable for their base types
- derived classes should adhere to the contract of their parent classes
- maintain behavioral consistency and avoid unexpected side effects

**9. Interface Segregation Principle (ISP)**
- clients should not depend on interfaces they don't use
- split large interfaces into smaller ones
- promote loose coupling and improve modularity

**10. Dependency Inversion Principle (DIP)**
- high level modules should depend on abstractions, not concrete implementations
- invert dependency flow to make code more flexible and testable
- utilize dependency injection and interfaces to decouple modules
