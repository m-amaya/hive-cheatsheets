# RxJS in Action
> By: Paul P. Daniels, Luis Atencio
> 
> Copyright: 2017

---

## Part I: Understanding Streams

### Chapter 1: Thinking Reactively

* Synchronous vs. Asynchronous Computing
  * Issues with Blocking Code
  * Non-Blocking Code with Callback Functions
  * Understanding Time and Space
  * Are Callbacks Out of the Picture?
  * Event Emitters
* Better Callbacks with Promises
* The Need for a Different Paradigm
* The Reactive Extensions for JavaScript
  * Thinking in Streams: Data Flows and Propagation
  * Introducing the RxJS Project
  * Everything is a Stream
  * Abstracting the Notion of Time from Your Programs
  * Components of an Rx Stream
* Reactive and Other Programming Paradigms

### Chapter 2: Reacting with RxJS

* Functional Programming as the Pillar of Reactive Programming
  * Functional Programming
  * The Iterator Pattern
* Stream's Data-Driven Approach
* Wrapping Data Sources with `Rx.Observable`
  * Identifying Different Sources of Data
  * Creating RxJS Observables
  * When and Where to Use RxJS
  * To Push or Not To Push
* Consuming Data with Observers
  * The Observer API
  * Creating Bare Observables
  * Observable Modules

### Chapter 3: Core Operators

* Evaluating and Cancelling Streams
  * Downside of Eager Allocation
  * Lazy Allocation and Subscribing to Observables
  * Disposing of Subscriptions: Explicit Cancellation
  * Cancellation Mismatch Between RxJS and Other APIs
* Popular RxJS Observable Operators
  * Introducing the Core Operators
* Sequencing Operator Pipelines with Aggregates
  * Self-contained Pipelines and Referential Transparency
  * Performance Advantages of Sequencing with RxJS

### Chapter 4: It's About Time You Used RxJS

* Why Worry about Time?
* Understanding Asynchronous Timing with JavaScript
  * Implicit Timing
  * Explicit Timing
  * The JavaScript Timing Interfaces
* Back to the Future with RxJS
  * Propagation
  * Sequential Time
* Handling User Input
  * Debouncing 101
  * Throttling
* Buffering in RxJS

## Part II: Observables in Practice

### Chapter 5: Applied Reactive Streams

* One for All, and All for One!
  * Interleave Events by Merging Streams
  * Preserve Order of Events by Concatenating Streams
  * Switch to the Latest Observable Data
* Unwinding Nested Observables: The Case of `mergeMap`
* Mastering Asynchronous Streams
* Drag and Drop with `concatMap`

### Chapter 6: Coordinating Business Processes

* Hooking into the Observable Lifecycle
  * Web Hooks and the Observer Pattern
  * Hooked on Observables
* Joining Parallel Streams with `combineLatest` and `forkJoin`
  * Limitations of using Promises
  * Combining Parallel Streams
  * More Coordination with `forkJoin`
* Building a Reactive Database
  * Populating a Database Reactively
  * Writing Bulk Data
  * Joining Related Database Operations
  * Reactive Databases

### Chapter 7: Error Handling with RxJS

* Common Error-Handling Techniques
  * Error Handling with Try/Catch
  * Delegating Erros to Callbacks
  * Errors and Promises
* Incompatibilities between Imperative Error-Handling Techniques and Functional and Reactive Code Bases
* Understanding the Functional Error-Handling Approach
* The RxJS Way of Dealing with Failure
  * Errors Propagated Downstream to Observers
  * Catching and Reacting to Errors
  * Retrying Failed Streams for a Fixed Number of Times
  * Reacting to Failed Retries

## Part III: Mastering RxJS

### Chapter 8: Heating Up Observables

* Introducing Hot and Cold Observables
  * Cold Observables
  * Hot Observables
* A New Types of Data Source: WebSockets
  * A Brief Look at WebSocket
  * A Simple WebSocket Server in Node.js
  * WebSocket Client
* The Impact of Side Effects on a Resubscribe or a Replay
  * Replay vs. Resubscribe
  * Replaying the Logic of a Stream
  * Resubscribing to a Stream
* Changing the temperature of an Observable
  * Producers as Thermometers
  * Making a Hot Observable Cold
  * Making a Cold Observable Hot
  * Creating Hot-By-Operator Streams
* Connecting One Observable to Many Observers
  * Publish
  * Publish with Replay
  * Publish Last

### Chapter 9: Toward Testable, Reactive Programs

* Testing is Inherently Built into Functional Programs
* Testing Asynchronous Code and Promises
  * Testing AJAX Requests
  * Working with Promises
* Testing Reactive Streams
* Making Streams Testables
* Scheduling Values in RxJS
* Augmenting Virtual Reality
  * Playing with Marbles
  * Fake it 'Til You Make It
  * Refactoring your Search Stream for Testability

### Chapter 10: RxJS in the Wild

* Building a Basic Banking Application
* Introduction to React and Redux
  * Rendering UI Components with React
  * State Management with Redux
* Redux-ing Application State
  * Actions and Reducers
  * Redux Store
* Building a Hot RxJS and Redux Store Adapter
* Asynchronous Middleware with RxJS Subject
  * RxJS Subjects
  * Building Epic, Reactive Middleware
* Bringing it All Home
* Parting Words