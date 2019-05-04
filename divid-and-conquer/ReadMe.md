## Anreas Hucks

### Motivation
    - 

    #### Not about
        - DDD
        - Generic Package Design
    #### A Generic Framework App
        - 

    ### Architecture patterns
        - not the focus of the talk
        - focus is hexagonal architecture
    #### Steps
        - Extracting out the domain
        - Create domain namespace and put all the doctrine pieces into it
            (doesnt have to be domain namespace)
        - Dedicated top level namespace
        - added a dedicated domain exception (Have a base exception per layer)
        - Extracted value objects
        - Use value objects to enforce correct values
        - 
    #### Tools
        - Deptrac
        - github.com/sensiolabs-de/deptrac

    ### Infrastructure Layer
        - move doctrine to the infrastructure layer
        - create repository interfaces
        ##### Extending EntityRepository
            - not extending it could confuse other developers?
    ### Decoupling Security with a security layer
        - 

    ### Validtion, Forms, and ViewModels
        - create DTO's that represent actions
        - These can be validated as per use case
        - Creates or Updates via a service using DTO and entity
    
    ### Missing Pieces
        - Did not use doctrine relations (You will have an array collection class a dependency)
        - Using Uuid library
            - Its ok to depend on libraries
        - Using Array collection as a dependency is another example
        - All of this only makes sense in long running projects
        - Short life projects can be coupled to a framework
    ### Be Pragmatic
        - We dont abstract doctrine
        - Its ok to directly work with doctrine
        - For the most part you dont have to do this
        - Dont hand entire entity to the template system
    ### Rules of thumb
        - model be self validating via value objects
    ### Going Farther
        - What about controllers?
            - Dont! because a controller is framework thing
            - Goes into testing mentality, you dont test controllers when unit testing.
