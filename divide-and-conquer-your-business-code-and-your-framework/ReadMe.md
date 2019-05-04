# Divide and Conquer Your Business Logic and Your Framework by Andreas Hucks

## Motivation

* Lots of consulting on legacy codebases

## Talk is not about

* DDD
* Generic Package Design

## A Generic Framework App

* A ROBOT app.
* CRUD app

## Problem

* Be able to switch out database, framework (but is rarely done, so not a problem)
* Tangled dependencies
* Direct access to entities
* Mixing responsibilities
* Controller uses ORM directly

## Why separate?

* Clean Layers
    * separate business code from framework
* Architecture Patterns
    * Components
    * Hexagonal
    * Not the point of this talk

## Extracting the Domain (business code)

* Create domain namespace with Doctrine folder in there
* Don't need a "framework" namespace - touch it as little as possible, keep framework's opinions
* Create value objects
    * enforce correct values 
    * Models self-validating
* Exceptions
    * Extend native PHP exceptions
    * Give domain logic names to your exceptions
    
## Deptrac

* github.com/sensiolabs-de/deptrac
* Static analyzer to enforce rules for dependencies between software layers
    * ex: "controllers may not depend on models"
    * QA tool for your CI/CD pipeline 
* Configured using YAML
    * define layers
    * define rules
    

    
    
    