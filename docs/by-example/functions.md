# Functions

Functions are the most basic way to make code reusable in Blakeney. Functions can be defined at a package or class level, or as a lambda function at scope level. There are two parts to defining a function:

 1. A function  __signature__ which defines the input and outputs of the function as _types_ (and occasionally some other attributes of the function).
 2. A function __body__ consisting of the code that implements the function

Function names must be `snake_case`.

## Example

    package examples
    
    def plus(a: int, b: int) -> int:
        return a + b
    
    def short_plus(a: int, b: int) => a + b
    
    def log_plus(a: int, b: int) -> void:
        std.print("Result: %s", plus(a, b))
     
    def main() -> int:
        result := short_plus(18, 24)
        log_plus(result, 58)
        
        lambda_fn := lambda x: int, y: int => x + y
        
        std.print("Hopefully, %d != %d!", result, lambda_fn(19, 5))
        
        return 0

##### Results

    Result: 100
    Hopefully, 42 != 24!

!!! Walkthrough
    
    __line x__ ``:
    _doc_
    
    __line x__ ``:
    _doc_
    
    __line x__ ``:
    _doc_
    
    __line x__ ``:
    _doc_    

## Function signatures

## Short-from vs long-form functions

## Lambda functions

## Example 2: Multiple return values

Tuples and implicit conversion of tuples can be used to return multiple values from a function.

    package examples
    
    def division_with_remainder(num: float, denom: int) -> (int, int):
        return (4, 5) #TODO

Here,  


##### Related material

 1. [Functions]()
 2. [Standard library]()


