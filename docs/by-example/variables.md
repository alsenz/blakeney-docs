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

## Declaration is initialisation

In other languages, it is possible to declare a variables without initialising it. This can lead to strange behaviours and bugs. For example, in Go, declared variables take a special "zero-value" if left uninitialised, and in C (or C++) the value of an uninitialised variable is _undefined behaviour_, which can lead to particularly pernicious bugs.

To avoid this, in Blakeney initialisation and declaration have to happen at the same time. Obviously there is a reason why most languages haven't adopted this protocol, but in Blakeney the down-sides of this are almost completely elmininated by other language features.

### Example: Conditional initialisation

One reason why you might want to declare a variable before initialising it is if its initialisation value depends on some runtime condition. Thankfully, in Blakeney there are 3 alternatives:

 1. Use a one-line [if expression][conditionals.md]
 2. Use a default value anyway, since it is easy for the compiler to optimise these away.
 3. Refactor the conditional part to a function

        def get_multiplier(is_negative: bool) -> int:
            return 42 if some_flag else -42
        
        def get_multiplier2(is_negative: bool) -> int:
            result := 42
            if is_negative:
                result = -result
             return result
        
        def get_widget(is_xlarge: bool) -> Widget:
            return Widget(build_widget_args(is_xlarge)...)
    
    

##### Related material

 1. [Functions]()
 2. [Standard library]()
 3. [Globals]()
 4. [Packages]()


