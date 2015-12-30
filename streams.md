# Introduction to streams

**Contents:**

1. What is a stream?
2. Collections vs. streams
3. Internal vs. external interation
4. Imtermediate vs. terminate operations

## What is a stream?

**Definition:** a stream is a sequence of elemnents from a source that supports data processing operations. This definition can be broken down step by step:

* **Sequence of elements:** Just like a collection, a stream provides an interface to a sequenced set of values of specific types. Since collections are data structures, so they're mostly about sorting and accessing elements with specific space/time complexities. Unlike collections, streams are about expressing computations such as filter, map, recduce, and so on. In short/to sum up/briefly, **collections are about data, streams about computations**.
* **Source**: streams consume from data-providing sources such as collections, arrays, I/O resources. Note, generating a stream from an ordered collections preseves the ordering
* **Data processing operations:** streams support database-like operations and common functional programming operations such as filter, map, reduce, match, sort, and on. **Streams operations can be executed sequentially or in parallel**. 


![alt text](https://github.com/StudyInDepth/Functional-Programming/blob/master/images/stream.png "Streams and Operations")

Streams also have two important characteristics:

* **Pipelining:** Many streams can return another streams, so operations can be chained and form a larger stream. This enables certain optimizations such as **laziness and short-curcuiting**. Pipelining operations can be viewed as database-like query on the data source. **Streams in Java are lazy**
* **Internal iteration:** In constrast to colletions, which are interated explicitly using an iterator, **streams operations do iteration behind the scence or internally**. By using internal iteration, streams operations can be easily and transparently parallelized to exploit all available cpu cores. 

## Collections vs. Streams?

Streams are conceptually fixed data structrues whose elements are **computed on demand**, adding and removing elements are not supported. In constrast, collections are eagerly constructed. 
![alt text](https://github.com/StudyInDepth/Functional-Programming/blob/master/images/streamsvscollections.png "Streams vs Operations")

Streams can be traversed only once, which is similar to iterators. To traverse all elements again, we have create a new stream from the initial data source, but this is only applied for repeatable data sources like collections, I/O it's quite different (that I don't know).

## External iteration vs. Internal iteration

Collections use external iteration while streams use internal iteration, streams do iteration, and we only have provide the function saying what's to be done. In addition, using an internal iteration, processing elements could be transpanrently done in parallel or in different order that can be more optimized. 

![alt text](https://github.com/StudyInDepth/Functional-Programming/blob/master/images/internalvsexternal.png "internal vs external")

## Stream operations

The Stream interface defines many operations that can be classified into two categories:
* Intermidate operations: map, filter, sorted, limit, ...
* Terminate operations: collect, reduce, forEach, ...

Intermidate operations return a stream as return type, which allows operations to be connected to form a query (like a database query). Intermidate operations are not performed until a terminate operation is invoked on the stream pipeline. This is because intermidate operations are usually merged and processed into a single pass (**Loop fusion**) by the terminate operation. **Streams are lazy and short-circuiting.**

Terminate operatiions produce a result from a stream pipeline. A result is non-stream value such as List, Integer, or void,... 

## Working with streams involves three items:
* A data source to perform a query
* Intermidate operations that forms a stream pipeline 
* Terminate operation that executes the stream pipeline and produces a result



 


