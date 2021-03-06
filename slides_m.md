
# The Legacy Code Change Algorithm

1. identify change points
2. find test points
3. break dependencies
4. write tests
5. make changes and refactor

----

# General Legacy Management Strategy 

(from http://www.objectmentor.com/resources/articles/WorkingEffectivelyWithLegacyCode.pdf)

* identify change points
* find an inflection point
* cover the inflection point
    * break external dependencies
    * break internal dependencies
    * write tests
* make changes
* refactor the covered code

_An inflection point is a narrow interface to a set of classes. If anyone changes any of 
the classes behind an inflection point, the change is either detectable at the inflection 
point, or inconsequential in the application._

----

# The Seam Model

_A **seam** is a place where you can alter behaviour in your program without editing in that place._


_Every seam has an **enabling point**, a place where you can make the decision to use one behaviour or another._

## Seam types

* _Preprocessing Seam_, e.g. macro preprocessor in C and C++
* _Link Seam_, e.g. replace classes by patching, i.e. putting them before the _real_ ones in the classpath
    * seam: the call to the class that is patched, e.g. new PersistentObject()
    * enabling point: the classpath
* _Object Seam_, e.g. replace an object by a new subclass, override an interesting function
    * enabling points: constructors, parameters
    
Sometimes, we have to change some code to make something a seam. E.g. static -> non static, can then be overridden.

----

# Effect Analysis

----

# How Do I Know That I'm Not Breaking Anything?

* lean on the compiler
* monitoring
* logging

----

# I Don't Understand the Code Well Enough to Change it

* notes / sketching
* listing markup
* scratch refactoring
* delete unused code

----

# Example: legacy singletons

----

# Misc

* low risk changes
