# Variables

Blakeney has support for statically typed variables. Variables are always declared by initialisation, and variables support multiple assignments of the same type.

## Example

    package examples
    
    def main() -> int:
        pi := 3.1415926
        multiplier := 4
        multiplier2: float = 4
        planck := float(0)
        
        planck = 6.626
        multiplier++
        two_pi := pi * multiplier
        
        std.printf("Planck's constant is: %f, it is of type: %s\n", planck, std.type(planck))
        std.printfln("Two pi as a float is: %f, and as an integer: %d\n", two_pi, two_pi)
        return 0

!!! Walkthrough
    
    __line 4__ `pi := 3.141`:
    _Create a variable, of type `float`, inferred from the value `3.141`_
    
    __line 5__ `multiplier := 4`:
    _Create a variable, of type `int`, inferred from the value `4`_
    
    __line 6__ `multiplier2: float = 4`:
    _Create another variable explicitly typed as a float, but with the value `4`_
    
    __line 7__ `planck := float(0)`:
    _Another way to coerce the `planck` variable to be of type float, by explicitly converting the `int` value `0`_
    
    __line 9__ `planck = 6.626`:
    _Assign a new value to the planck float variable_

## First Subtitle

## Second Subtitle

##### Related material

 1. [Functions]()
 2. [Standard library]()
 3. [Globals]()
 4. [Packages]()


