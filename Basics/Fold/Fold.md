# Fold

> Fold takes data in one format and gives it back to you in another. Please refer to [fold, foldLeft, and foldRight](https://coderwall.com/p/4l73-a/scala-fold-foldleft-and-foldright) for more information.
> 

```jsx
val list = List(1, 2, 3, 4, 5)
val sum = list.fold(0)((x, y) => x + y)
```

## fold, foldLeft, foldRight

- `foldLeft()`iterates from left to right
- `foldRight()`iterates from right to left
- `fold()`does not go in any particular order
    - start value must be a supertype of the object you are folding.
        
        e.g. Int is a supertype of List[Int]
        
    - start value must be neutral(not affect the result)