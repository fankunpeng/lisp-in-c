## A rudimentary Lisp interpreter and compiler, inspired by Structure and Interpretation of Computer Programs, [exercises 5.51 and 5.52](http://mitpress.mit.edu/sicp/full-text/book/book-Z-H-35.html#%_thm_5.51)

### Exercise 5.51.

"Develop a rudimentary implementation of Scheme in C (or some other
low-level language of your choice) by translating the explicit-control
evaluator of section 5.4 into C. In order to run this code you will
need to also provide appropriate storage-allocation routines and other
run-time support."

C is a bit higher-level than the register machine language that the
explicit control evaluator is written in, so I basically translated
the meta-circular evaluator to C instead.

### Exercise 5.52.

"As a counterpoint to exercise 5.51, modify the compiler so that it
compiles Scheme procedures into sequences of C instructions. Compile
the metacircular evaluator of section 4.1 to produce a Scheme
interpreter written in C."

The compiler here is basically a translator which takes as input
register machine code and emits C.

### features/bugs:

* The repl doesn't handle two s-expression on a one line, ignores the second one.
* Primitives don't check for arity, so (quote foo bar) is just foo, and not an error.
* No tail-call optimization
* No garbage collection
* No user-defined macros, altho a macro system is in place for "system" macros
* Not much error checking
    * bombs on bad filenames to load

### see also:

* [An Incremental Approach to Compiler Construction](http://scheme2006.cs.uchicago.edu/11-ghuloum.pdf)
* [90 Minute Scheme to C Compiler](http://www.iro.umontreal.ca/~boucherd/mslug/meetings/20041020/minutes-en.html)
* [A tiny self-hosting Lisp-to-C compiler](https://github.com/darius/ichbins)
* [Scheme from Scratch](http://michaux.ca/articles/scheme-from-scratch-introduction)
