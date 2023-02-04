# ConcurrentHashMap

> **Thread safe**
> 

## ****ConcurrentHashMap 1.7****

- Once the number of `Segment` is initialized, it **cannot be changed**. The default number of Segment is **16**, which means ConcurrentHashMap supports up to **16 thread concurrency** by default.
- `Segment.put`uses `tryLock()` to obtain lock.

## ****ConcurrentHashMap 1.8****

- `Node`is empty, use **spinning** lock to write data.
- `LinkedList`or `RB Tree` , use `synchronized` to write data.