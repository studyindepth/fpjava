# Introduction to streams

Contents:

1. What is a stream?
2. Collections vs. streams
3. Internal vs. external interation
4. Imtermediate vs. terminate operations

## What is a stream?

Definition: a stream is a sequence of elemnents from a source that supports data processing operations. This definition can be broken down step by step:

* Sequence of elements: Just like a collection, a stream provides an interface to a sequenced set of values of specific types. Since collections are data structures, so they're mostly about sorting and accessing elements with specific space/time complexities. Unlike collections, streams are about expressing computations such as filter, map, recduce, and so on. In short/to sum up/briefly, collections are about data, streams about computations.
* Source: streams consume from data-providing sources such as collections, arrays, I/O resources. Note, generating a stream from an ordered collections preseves the ordering
* Data processing operations: streams support database-like operations and common functional programming operations such as filter, map, reduce, match, sort, and on. Streams operations can be executed sequentially and in parallel. 

Streams also have two important characteristics:

* Pipelining: Many streams can return another streams, so operations can be chained and form a larger stream. This enables certain optimizations such as laziness and short-curcuiting. Pipelining operations can be viewed as database-like query on the data source.
* Internal iteration: In constrast to colletions, which are interated explicitly using an iterator, streams operations do iteration behind the scence or internally. By using internal iteration, streams operations can be easily and transparently parallelized to exploit all available cpu cores. 


