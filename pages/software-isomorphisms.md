# Software Isomorphisms

A computer is a machine that executes a sequence of instructions. The first programmers wrote these instructions directly, first as machine code and then as assembly language (essentially machine code in a human readable format). However, programmers quickly figured out how to create abstractions over machine code, leading to "high-level languages" like COBOL, FORTRAN, LISP, and C, and we've been creating [more and more languages](https://en.wikipedia.org/wiki/Generational_list_of_programming_languages) ever since.

Today, most programmers design and implement software systems without ever thinking about machine code. Because there are so many high-level languages and programming paradigms, there are many different ways to produce the same or similar machine code. We often debate about which programming language or programming paradigm is better -- Functional or imperative? Procedural or object-oriented? Python or Java? React or Angular? The divisions go on.

While you can compare programming languages across many different factors, two of the most common factors are performance (how efficient is the machine code produced by your language's compiler?) and productivity (how quickly can you solve problems with your language?). In this article, I'd like to explore some different ways to produce the same (or similar) machine code from high-level languages, also known as **software isomorphisms**. These isomorphisms are useful not only to demonstrate how different programming paradigms can have interesting parallels, but also to reason about how one approach might be "better" than another in certain situations (and vise versa).

This article is inspired by a [similar article series](https://blog.ploeh.dk/2018/01/08/software-design-isomorphisms/) by Mark Seemann.

TODO

- Void, unit type
- Procedural, object-oriented
- Argument list, parameter object, tuple, currying
- Objects, closures (e.g. Builder, Command, Strategy)
- Inheritance, composition
- Tester-doer, try-parse, Option/Result
