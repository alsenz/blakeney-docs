# Title

One line

## Example

    package examples
    
    def main() -> int:
        return 0

## Example 2: How the `std.type(...)` function is implemented

    package std
    
    meta:
        
        def type_id(t: std.type) -> std.type => t
    
    def type<T>(_: T) => meta: type_id<T>()

!!! Walkthrough
    
    __line 7__ `def type<T>(_: T) => meta: type_id<T>()`:
    _Uses generic type inference from the (unused) first argument to call `type_id` meta function._
    
    __line 5__ `def type_id(t: std.type)`:
    _Meta function calling rules convert type parameters in the runtime language to function arguments in the metalanguage_
    
    __line 5 (cont'd)__ `-> std.type => t`:
    _Simple return the type argument instance to the runtime language at compile time._

## First Subtitle

## Second Subtitle

##### Related material

 1. [Functions]()
 2. [Standard library]()


