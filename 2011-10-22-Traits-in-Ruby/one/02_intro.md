!SLIDE

# Оригинальная идея:
[Очень научная pdf на антимонгольском языке про концепцию traits](http://web.archive.org/web/20071008161120/http://www.iam.unibe.ch/%7Escg/Archive/Papers/Scha02bTraits.pdf)

!SLIDE bullets incremental transition=fade

# Что позволяют:

* A trait provides a set of methods that implement behaviour.
* A trait requires a set of methods that parameterize the provided behaviour.
* Traits do not specify any state variables, and the methods provided by traits never directly access state variables.

!SLIDE bullets incremental transition=fade

# Что позволяют (продолжение):

* Traits can be composed: trait composition is symmetric and conflicting methods are excluded from the composition.
* Traits can be nested, but the nesting has no semantics for classes - nested traits are equivalent to flattened traits.
