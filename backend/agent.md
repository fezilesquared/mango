Microservice Architechture
Each Microservice is a project ih the Mango.sln solution

The following applies to all projects apart from the Mango.Common
Each project follows the Clean Architecture for now
Meaning that each Project is at the very least these folders: 

- Domain: The base folder every other folder accesses. This has core things used throught the project like 
Entities and Dtos
    - Entities
    - Dtos 
- Infrastructure: This has things directly related to external communication. So Http clients, Azure service bus clients, 
entity framework related things and also abstractions like Repositories
    - Data
        - Migrations            
        - Repositories 
            - Interfaces 
            - Implementations
        - UnitOfWork
            IUnitOfWork.cs
            UnitOfWork.cs
        DbContext.cs         
    - Http
        - Clients
        - Services
            - Interfaces 
            - Implementations
    - Message Bus (Only for Projects that are Message Bus Aware)
        - Clients 
        - Publishers
            - Interfaces
            - Implementations
        - Handlers
            - Interfaces
            - Implementations
        Topics.cs      
  
- Application: This is where the Services that manage interactions between the Domain Layer and Interface Layers live
    - Services
        - Interfaces
        - Implementations 
    - Mapping 
        - Configurations
        - Mappers

The presentation Layer doesn't have it's own folder. Since each project is a .net core web api project 

We also have a Common Folder for things that are uses through out the project but aren't common between microservices 
    - Helpers
    - Constants
    - Configuration
    - Extensions
    - Validation
Next We have: 
Validation: For FluentValidation Definitions


     

