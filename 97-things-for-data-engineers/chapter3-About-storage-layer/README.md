# About Storage Layer
The main purpose of abstraction in software is to hide complexity. A software is built on top of abstraction layers without needing knowing everything how they are implemented.

It's useful but not necessary to actually go through these details at least once. For example, understanding Assembly language, compilers will make you better programme although we don't use them in our daily basis. 

A native query engine will load data in memory and apply the filters and other experssions. Naturally, we want to avoid loading anything that will be discarded as part of query processing. This saves I/O cost as well as CPU cost by avoiding the subsequent deserialization. We also want to reduce the data footprint, so the data costs less to store and is faster to retrieve. A com‐ bination of encodings and compression provides a trade-off between decreasing I/O cost and increasing CPU cost. 


## Pushdown
Those implementation details are hidden behind which are commonly known as `pushdown`. It push query operations into storage layer to minimize the cost of data loading. 

### Projection Pushdown
This kind of `pushdown` consists of reading only columns requested. 

### Predicate Pushdown
This kind of `pushdown` consists of avoiding deserializing rows that to be discarde by filtering expresssion. 

## Example:
Different storage characteristics will impact the performance of the `pushdown`. 
1. Columnar layouts (Apache parquet) enable projection pushdown with better encoding and compression. 
2. Statistics like max/min value enable predicate push down. 
3. Sorting and Partitioning data on different columns (Apache Icebarg) will make both compression and predicate pushdown more efficient.
