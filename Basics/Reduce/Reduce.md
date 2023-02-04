# Reduce

> Refer to [Why is a combiner needed for reduce method](https://stackoverflow.com/questions/24308146/why-is-a-combiner-needed-for-reduce-method-that-converts-type-in-java-8) for more information.
> 

### Two-Arg reduction

```java
T reduce(T identity,
         BinaryOperator<T> accumulator)
			   //（T, T) -> T
```

- The identity value is "**accumulated**" with every T values
    
    ```java
    T result = identity;   
    for (T element : this stream)       
    		result = accumulator.apply(result, element)   
    return result;
    ```
    

### Three-Arg reduction

```java
<U> U reduce(U identity,
             BiFunction<U,? super T,U> accumulator,
				     //（U, T) -> U
             BinaryOperator<U> combiner)
             //（U, U) -> U
```

- The combiner **combines** the multiple intermediate results of type U into a single result of type U
    
    The intermediate values are of type U instead of type T because we have N threads reduce the T values in its segment into N intermediate values of type U.