# API

## `rxjs`

* `bindCallback`: Converts a callback API to a function that returns an Observable.
* `bindNodeCallback`: Converts a Node.js-style callback API to a function that returns an Observable.
* `combineLatest`: Combines multiple Observables to create an Observable whose values are calculated from the latest values of each of its input Observables.
* `concat`: Creates an output Observable which sequentially emits all values from given Observable and then moves on to the next.
* `defer`: Creates an Observable that, on subscribe, calls an Observable factory to make an Observable for each new Observer.
* `forkJoin`: Accepts an `Array` of `ObservableInput` or a dictionary `Object` of `ObservableInput` and returns an `Observable` that emits either an array of values in the exact same order as the passed array, or a dictionary of values in the same shape as the passed dictionary.
* `from`: Creates an Observable from an Array, an array-like objects, a Promise, an iterable object, or an Observable-like object.
* `fromEvent`: Creates an Observable that emits events of a specific type coming from the given event target.
* `fromEventPattern`: Creates an Observable from an arbitrary API for registering event handlers.
* `generate`
  * Generates an observable sequence by running a state-driven loop producing the sequence's elements, using the specified scheduler to send out observer messages.
  * Generates an Observable by running a state-driven loop that emits an element on each iteration.
  * Generates an observable sequence by running a state-driven loop producing the sequence's elements, using the specified scheduler to send out observer messages.
  * Generates an observable sequence by running a state-driven loop producing the sequence's elements, using the specified scheduler to send out observer messages.
* `identity`
* `iif`: Decides at subscription time which Observable will actually be subscribed.
* `interval`: Creates an Observable that emits sequential numbers every specified interval of time, on a specified `SchedulerLike`.
* `isObservable`: Tests to see if the object is an RxJS `Observable`.
* `merge`: Creates an output Observable which concurrently emits all values from every given input Observable.
* `noop`
* `of`: Converts the arguments to an observable sequence.
* `onErrorResumeNext`: When any of the provided Observable emits on complete or error notification, it immediately subscribes to the next one that was passed.
* `pairs`: Convert an object into an Observable of `[key, value]` pairs.
* `partition`: Splits the source Observable into two, one with values that satisfy a predicate, and another with values that don't satisfy the predicate.
* `pipe`
* `race`: Returns an Observable that mirrors the first source Observable to emit an item.
* `range`: Creates an Observable that emits a sequence of numbers within a specified range.
* `scheduled`: Converts from a common `ObservableInput` type to an observable where subscription and emissions are scheduled on the provided scheduler.
* `throwError`: Creates an Observable that emits no items to the Observer and immediately emits an error notification.
* `timer`: Creates an Observable that starts emitting after an `dueTime` and emits ever increasing numbers after each `period` of time thereafter.
* `using`: Creates an Observable that uses a resource which will be disposed at the same time as the Observable.
* `zip`: Combines multiple Observables to create an Observable whose values are calculated from the values, in order, of each of its input Observables.

## `rxjs/operators`

* `audit`: Ignores source values for a duration determined by another Observable, then emits the most recent value from the source Observable, then repeats this process.
* `auditTime`: Ignores source values for `duration` milliseconds, then emits the most recent value from the source Observable, then repeats this process.
* `buffer`: Buffers the source Observable values until `closingNotifier` emits.
* `bufferCount`: Buffers the source Observable values until the size hits the maximum `bufferSize` given.
* `bufferTime`: Buffers the source Observable values for a specific time period.
* `bufferToggle`: Buffers the source Observable values starting from an emission from `openings` and ending when the output of `closingSelector` emits.
* `bufferWhen`: Buffers the source Observable values, using a factory function of closing Observables to determine when to close, emit, and reset the buffer.
* `catchError`: Catches errors on the observable to be handled by returning a new observable or throwing an error.
* `combineAll`: Flattens an Observable-of-Observables by applying `combineLatest` when the Observable-of-Observables completes.
* `concatAll`: Converts a higher-order Observable into a first-order Observable by concatenating the inner Observables in order.
* `concatMap`: Projects each source value to an Observable which is merged in the output Observable, in a serialized fashion waiting for each one to complete before merging the next.
* `concatMapTo`: Projects each source value to the same Observable which is merged multiple times in a serialized fashion on the output Observable.
* `count`: Counts the number of emissions on the source and emits that number when the source completes.
* `debounce`: Emits a value from the source Observable only after a particular time span determined by another Observable has passed without another source emission.
* `debounceTime`: Emits a value from the source Observable only after a particular time span has passed without another source emission.
* `defaultIfEmpty`: Emits a given value if the source Observable completes without emitting any `next` value, otherwise mirrors the source Observable.
* `delay`: Delays the emission of items from the source Observable by a given timeout or until a given Date.
* `delayWhen`: Delays the emission of items from the source Observable by a given time span determined by the emissions of another Observable.
* `dematerialize`: Converts an Observable of `Notification` objects into the emissions that they represent.
* `distinct`: Returns an Observable that emits all items emitted by the source Observable that are distinct by comparison from previous items.
* `distinctUntilChanged`: Returns an Observable that emits all items emitted by the source Observable that are distinct by comparison from the previous item.
* `distinctUntilKeyChanged`: Returns an Observable that emits all items emitted by the source Observable that are distinct by comparison from the previous item, using a property accessed by using the key provided to check if the two items are distinct.
* `elementAt`: Emits the single value at the specified `index` in a sequence of emissions from the source Observable.
* `endWith`: Returns an Observable that emits the items you specify as arguments after it finishes emitting items emitted by the source Observable.
* `every`: Returns an Observable that emits whether or not every item of the source satisfies the condition specified.
* `exhaust`: Converts a higher-order Observable into a first-order Observable by dropping inner Observables while the previous inner Observable has not yet completed.
* `exhaustMap`: Projects each source value to an Observable, which is merged in the output Observable only if the previous projected Observable has completed.
* `expand`: Recursively projects each source value to an Observable which is merged in the output Observable.
* `filter`: Filter items emitted by the source Observable by only emitting those that satisfy a specified predicate.
* `finalize`: Returns an Observable that mirrors the source Observable, but will call a specified function when the source terminates on complete or error.
* `find`: Emits only the first value emitted by the source Observable that meets some condition.
* `findIndex`: Emits only the index of the first value emitted by the source Observable that meets some condition.
* `first`: Emits only the first value (or the first value that meets some condition) emitted by the source Observable.
* `flatMap`: Projects each source value to an Observable which is merged in the output Observable.
* `groupBy`: Groups the items emitted by an Observable according to a specified criterion, and emits these grouped items as `GroupedObservables`, one `GroupedObservable` per group.
* `ignoreElements`: Ignores all items emitted by the source Observable and only passes calls of `complete` or `error`.
* `isEmpty`: Emits false if the input observables emits any values, or emits true if the input observable completes without emitting any values.
* `last`: Returns an Observable that emits only the last item emitted by the source Observable. It optionally takes a predicate function as a parameter, in which case, rather than emitting the last item from the source Observable, the resulting Observable will emit the last item from the source Observable that satisfies the predicate.
* `map`: Applies a given `project` function to each value emitted by the source Observable, and emits the resulting values as an Observable.
* `mapTo`: Emits the given constant value on the output Observable every time the source Observables emits a value.
* `materialize`: Represents all of the notifications from the source Observable as `next` emissions marked with their original types within `Notification` objects.
* `max`: The `max` operates on an Observable that emits numbers (or items that can be compared with a provided function), and when source Observable completes it emits a single item: the item with the largest value.
* `mergeAll`
* `mergeMap`
* `mergeMapTo`
* `mergeScan`
* `min`
* `multicast`
* `observeOn`
* `onErrorResumeNext`
* `pairwise`
* `pluck`
* `publish`
* `publishBehavior`
* `publishLast`
* `publishReplay`
* `reduce`
* `refCount`
* `repeat`
* `repeatWhen`
* `retry`
* `retryWhen`
* `sample`
* `sampleTime`
* `scan`
* `sequenceEqual`
* `share`
* `shareReplay`
* `single`
* `skip`
* `skipLast`
* `skipUntil`
* `skipWhile`
* `startWith`
* `subscribeOn`
* `switchAll`
* `switchMap`
* `switchMapTo`
* `take`
* `takeLast`
* `takeUntil`
* `takeWhile`
* `tap`
* `throttle`
* `throttleTime`
* `throwIfEmpty`
* `timeInterval`
* `timeout`
* `timeoutWith`
* `timestamp`
* `toArray`
* `window`
* `windowCount`
* `windowTime`
* `windowToggle`
* `windowWhen`
* `withLatestFrom`
* `zipAll`

## `rxjs/fetch`

* `fromFetch`

## `rxjs/webSocket`

* `webSocket`