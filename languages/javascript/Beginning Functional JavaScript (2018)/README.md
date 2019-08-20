# Beginning Functional JavaScript, 2nd Edition
> Uncover the Concepts of Functional Programming with EcmaScript 8
> 
> By: Anto Aravinth, Srikanth Machiraju
> 
> Copyright: 2018

---

### Chapter 1: Functional Programming in Simple Terms

* What is Functional Programming? Why Does it Matter?
  * Functions vs. Methods in JavaScript
* Referential Transparency
* Imperative, Declarative, Abstraction
* Functional Programming Benefits
* Pure Functions
  * Pure Functions Lead to Testable Code
  * Reasonable Code
  * Parallel Code
  * Cachable
  * Pipelines and Composable

### Chapter 2: Fundamentals of JavaScript Functions

* ECMAScript: A Bit of History
* Creating and Executing Functions
  * First Function
  * Strict Mode
  * Return Statement is Optional
  * Multiple Statement Functions
  * Function Arguments

### Chapter 3: Higher Order Functions

* Understanding Data
  * Understanding JavaScript Data Types
  * Storing a Function
  * Passing a Function
  * Returning a Function
* Abstraction and Higher Order Functions
  * Abstraction Definitions
  * Abstraction via Higher Order Functions
* Higher Order Functions in the Real World
  * `every` Function
  * `some` Function
  * `sort` Function

### Chapter 4: Closures and Higher Order Functions

* Understanding Closures
  * What are Closures?
  * Remembering Where it is Born
  * Revisiting `sortBy` Function
* Higher Order Functions in the Real World (Continued)
  * `tap` Function
  * `unary` Function
  * `once` Function
  * `memoize` Function
  * `assign` Function

### Chapter 5: Being Functional on Arrays

* Working Functionally on Arrays
  * `map`
  * `filter`
* Chaining Operations
  * `concatAll`
* Reducing Function
  * `reduce` Function
* Zipping Arrays
  * `zip` Function

### Chapter 6: Currying and Partial Application

* A Few Notes on Terminology
  * Unary Function
  * Binary Function
  * Variadic Functions
* Currying
  * Currying Use Cases
  * A `logger` Function: Using Currying
  * Revisit Curry
  * Back to `logger` Function
* Currying in Action
  * Finding a Number in Array Contents
  * Squaring an Array
* Data Flow
  * Partial Application
  * Implementing `partial` Function
  * Currying vs. Partial Application

### Chapter 7: Composition and Pipelines

* Composition in General Terms
  * Unix Philosophy
* Functional Composition
  * Revisiting `map`, `filter`
  * `compose` Function
* Playing with the `compose` Function
  * `curry` and `partial` to the Rescue
  * `compose` Many Functions
* Pipelines and Sequence
  * Implementing `pipe`
  * Odds on Composition
  * The Pipeline Operator
  * Debugging Using the `tap` Function

### Chapter 8: Fun with Functors

* What is a Functor?
  * Functor is a Container
  * Implementing `map`
* MayBe
  * Implementing MayBe
  * Simple Use Cases
  * Real-World Use Cases
* Either Functor
  * Implementing Either
  * Reddit Example Either Version
* Word of Caution: Pointed Functor

### Chapter 9: Monads in Depth

* Getting Reddit Comments for Our Search Query
* The Problem:
  * Implementation of the First Step
  * Merging Reddit Calls
  * Problem of Nested/Many Maps
* Solving the Problem via `join`
  * `join` Implementation
  * `chain` Implementation

### Chapter 10: Pause, Resume, and Async with Generators

* Async Code and Its Problem
  * Callback Hell
* Generators 101
  * Creating Generators
  * Caveats of Generators
  * `yield` Keyword
  * `done` Property of Generator
  * Passing Data to Generators
* Using Generators to Handle Async Calls
  * Generators for Async: A Simple Case
  * Generators for Async: A Real-World Case
* Async Functions in ECMAScript 2017
  * Promise
  * Await
  * Async
  * Chaining Callbacks
  * Error Handling in Async Calls
  * Async Functions Transpiled to Generators

### Chapter 11: Building a React-Like Library

* Immutability
* Building a Simple Redux Library
* Building a Framework Like HyperApp
  * Virtual DOM
  * JSX
  * JS Fiddle
  * CreateActions
  * Render
  * Patch
  * Update
  * Merge
  * Remove

### Chapter 12: Testing and Closing Thoughts

* Introduction
* Types of Testing
* BDD and TDD
* JavaScript Test Frameworks
  * Testing Using Mocha
  * Mocking Using Sinon
  * Testing with Jasmine
* Code Coverage
* Linting
* Unit Testing Library Code
* Closing Thoughts