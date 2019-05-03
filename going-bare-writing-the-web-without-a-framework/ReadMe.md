# Going Bare - Writing the Web Without a Framework by Sammy Kaye Powers

@SammyK
https://joind.in/talk/4b6f9

## Pros and Cons for using a Web Framework

* Pros
    * Fast
    * Community
* Cons
    * Legacy codebase
    * Easy to tightly couple to framework
    
    
## How to go bare?

* Use Components
    * Choose your favorite components
    * Install using composer
* A framework is like a bag of candy where you don't always get what you like
* Components don't just magically start working together
    * Learn to boilerplate and bootstrap your code

### There are no conventions, so this is one way to do things:
 
1. Make an empty composer.json
2. Make a folder src/
3. Add autoloading (go psr-4!)
4. Install your components and tie them together (CLI first)
    - Install a console component
    - Write some bootstrap code
    - Create your command
5. Http
    - Install a DI Container (use a singleton for it)
    - Boot up your app.
6. Unit Tests

### How to choose components?

* Try more than one framework to learn pros and cons of different frameworks.
* Search packagist.org (make sure has good docs and is actively maintained)


