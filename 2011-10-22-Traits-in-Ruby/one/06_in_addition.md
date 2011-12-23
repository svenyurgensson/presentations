!SLIDE bullets incremental transition=fade
## Caveats:

* Ruby doesn't fully fit into traits conception
* Restrictions of language possibilities
* Restrictions of interpretator
* Maybe in 2.0 ?? 
* Who know …

!SLIDE bullets incremental transition=fade
## In addition:

* Stop using _alias_method_chain_
* _alias_method_chain_ was invented simply because some people did not know about this
  powerful feature of Ruby's object model back in 2005

!SLIDE small bullets incremental transition=fade
## Modularize your code!!

* Ruby object model is beautiful and rich. Learn it as good as you can.

* Using rich object model and all the features built into it is way better
  compared to inventing your own OOP (e.g. alias_method_chain) or just
  not following three main ideas of OOP (incapsulation, inheritance, polymorphism)

* Modules are _the_ cornerstone of Ruby's object model

* Module inclusion results in an anonymous class being created in hosting class' inheritance chain

* Because of previous point, yon can call super from Module methods.
