## Getting Started

### How observables, observers and subscriptions work together?
Observables basically acts like a wrapper of some data source - typically a streams of values. It is the concept of date that we usually use for asynchronous data.

So, we have a stream of data, possiblily a asynchronous or a  multiple values over a time. And, now we wanna do something whenever a new value occurs. That is a job of observers. The observers are there to execute the code whenever we received a new value or maybe errors.

Subscription basically means, with one method (subscribe method), we tell an observable our wrapper around that stream of values that someone is caring about these values.
Observer on the other hand implements three methods  - next(),error() and complete().
The next() method is called by the observables whenever a new value is emitted. The error() will be called whenever a observables throws an errors.And  complete() methos is called whenever the observables is done, so whenever we know that no more values will be emitted in the future.<br>

<img src="https://user-images.githubusercontent.com/47861774/57973322-df65ff80-79c6-11e9-8235-35c3e4ffbb2e.png" heigth="300px"
width="700px">

## How did observables knows that it should call next(), error() or complete() ?
Well, that is the kind of contract between  observables and observers signed throught the subscription.The observables knows that it could fired a next(), error() or a complete() methods on observers. And, the observers on the other hand knows that the observables will fire only one of theree methods 
