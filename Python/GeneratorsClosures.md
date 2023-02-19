# Generators & Closures

-	**Generators**: A piece of specialized code able to produce a series of values, and to control the iteration process
    -	Returns a series of values and is implicitly invoked more than once
-	**Closure**: A technique allowing values to be stored despite that where they have been created no longer not exists
    -	Invoked in exactly the same way that it was declared
-	**Iterator Protocol**: To be an iterator an object must conform to the rules imposed by the context of the `for` and `in` statements
    -	**Iterator**: Object of a class that must provide at least the following two methods:
        1.	`__iter__()`: Returns the object itself, invoked once. Needed for python to start iteration
        2.	`__next__()`: Returns the next value (2nd, 3rd, 4th… and so on) of series. Invoked by `for`/`in` statements, to pass through to next iteration, when no more values to iterate the method should raise the `StopIteration` exception 
-	`return` **statement**: Cannot turn a function into a generator, as cannot save and restore its state between subsequent invocations
    ```
    def fun(n):
        for i in range(n):
            return i
    ```
-	`yield` **statement**: Can only be used inside a function, to turn the function into a generator
    -	Suspends function execution, causing it to return the yield’s argument as a result 
      ```
      def fun(n):
          for i in range(n):
              yield i
      ```
-	**Conditional Expression**: Built using the if-else operator
-	**List Comprehension**: Becomes generator when used inside parentheses
-	lambda: An anonymous function intended to evaluate a result.
-	`map(function, list)`: Applies the function passed by its first argument to all its second argument's elements, and returns an iterator delivering all subsequent function results.
-	`filter()`: Filters its second argument while being guided by directions flowing from the function specified as the first argument.
    -	Elements returning True from the function will pass the filter, those returning False will not.
-	`list()`: Converts data into a list, such as resulting iterator in a loop in the `map()` and `filter()` functions
