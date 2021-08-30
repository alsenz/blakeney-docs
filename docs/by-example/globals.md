# Globals

Globals provide a way to manage constants at package level, or statically at class level. They hold constants and are visible to all scopes in the package. All globals must be `CAPS_UNDERSCORE_CASE` or a compiler error will be thrown.

Because in Blakeney, only type definitions (classes, functions, etc.) are permitted at global scope, a global definition is actually implemented as an atomic _type_ uniquely corresponding to the value it holds. A convenient consequence of this is that constants are distinguishable by value in the metalanguage as types (see [Metalanguage](metalanguage.md)).


## Example

    package examples
    
    MEANING_OF_LIFE := 42
    THE_QUESTION: float = 6 * 9
    SMALL_NUMBER := 3

    class Writer:
        TMP_DIRECTORY := "/tmp/examples"
    
    def main() -> int:
        
        std.print("The meaning of life is: %d, but THE_QUESTION has a strange type: %s.", MEANING_OF_LIFE, std.type(THE_QUESTION)))
        
        the_question := float(0) + THE_QUESTION
        std.print("When used, THE_QUESTION implicitly converts to a %s type with the value %f")
        
        # Print "have a nice day" SMALL_NUMBER number of times
        meta: for i in range SMALL_NUMBER:
            std.print("%d: have a nice day!", i)
        
        print("ALL_CAPS class members behave like globals too: %s", Writer.TMP_DIRECTORY)
        
        return 0

##### Results:

    The meaning of life is: 42, but THE_QUESTION has a strange type: std.atomic<float>[54.000].
    When used, THE_QUESTION implicitly converts to a float type with value 54.000
    0: have a nice day
    1: have a nice day
    2: have a nice day
    ALL_CAPS class members behave like globals too: /tmp/examples

!!! Walkthrough
    
    __line x__ ``:
    _doc_
    
    __line x__ ``:
    _doc_
    
    __line x__ ``:
    _doc_
    
    __line x__ ``:
    _doc_    

## Basic properties

## What does atomic&lt;float&gt;[54.000] actually mean?

## Example 2: Calling a meta function

##### Related material

 1. [Packages](packages.md)
 2. [Variables](variables.md)
 3. [Metalanguage](metalanguage.md)


