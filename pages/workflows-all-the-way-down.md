# Workflows All the Way Down

*Epistemic status: work in progress*

One day I felt the unction to write some sort of grand theory. I had been using Nextflow for a while and I began to see "workflows" everywhere (I still do, but we'll get into that later), so I thought I might be able to make some deeper observation about the nature of programming and computation.

I never did write that grand theory. I created a page with a few ideas, and I just kept adding ideas to the list, but never made time to write the damn thing. Meanwhile, my proto-theory was apparently taking on more and more aspects, expanding as I found new topics that sparked my interest. This is that page, by the way, and you can check the commit history for evidence.

I think what really happened is that I finally had time to get exposed to the wider software industry after years of focusing on a few niche projects for my doctoral research.

Still, I don't want these ideas or the spark they gave me to fade away. So I'm just going to log the good ones as I discover them, with hope that a greater pattern might emerge, that grand journey towards humane programming, and unbounded computation.

## Workflows All the Way Down

A workflow is a graph (i.e. network) of tasks connected to each other based on their dependencies. If task A is connected to task B, that means that B depends on A in some way.

It turns out that [you can represent just about anything with a graph](./101-graph-examples.md), but right now I just want to focus on *workflow* graphs.

Workflows are everywhere. If you think about your work, the activities you do throughout the day, the greater systems in which you take part, you will almost certainly discover a few workflows.

Let's just start with computers and work our way up the stack:

- Computers are made of electrical circuits, in which differences of electrical potential (voltage) causes "current" to "flow" between electrical components through some conduit (e.g. copper wire). That's *literally* a workflow.

- The electrical circuits form *digital* circuits, which do the same thing but we usually model tham as *digital signals* propagating through various *logical gates*. Also a workflow.

- Computer programs (software) take this idea to yet another level, in which data flows through a sequence of operations. Like an electrial component or logic gate, every assembly instruction has *inputs* and *outputs*, and multiple instructions can be connected into bigger and bigger computations, without limit.

From there it just keeps going. Instructions can be combined into programs. Programs can be combined into scripts and workflows. Workflows can be combined into bigger workflows, or may become part of "human" workflows. Humans and computers can be combined to form organizations. Organizations can be combined to form entire economies.

When you cook something, you are in a sense executing a workflow. There are inputs (ingredients) and outputs (food), and there may be many intermediate steps involving manual labor, cooking appliances, tools, and so on. While recipes are usually written as a list of step-by-step instructions, sometimes you can do multiple steps in parallel if they don't depend on each other, like preparing a salad while waiting for some meat to cook. Cooking is actually a rather good analogy for computation!

## Functional programming

What if software could be written as composite functions, like a mathematical expression? Inputs transformed into outputs, all the way down and all the way up. Functional languages are said to be easier to read and debug. With statically-typed functional languages like Haskell and OCaml, it's often said that "if the code compiles, it's probably correct."

Functional languages typically impose two constraints: (1) no side effects, (2) no mutation. These constraints make the code easier to read and understand, but the problem is that sooner or later you have to mutate things and you have to do side effects (printing to the console, writing to a file, sending an HTTP request, etc).

As a result, functional programming has had more impact as an approach to writing code rather than through purely functional languages. That is, you can write most of your code as pure functions, regardless of the language, and then use an imperative approach in cases where you need more performance or need to do I/O. Of course, your C++ or Java compiler won't tell you when a variable is mutated or a function has a side effect, even as a hint. Some languages like Rust make variables immutable by default and require mutable variables to be explicitly marked as such, which is a nice improvement.

Another interesting trend is that mainstream languages have slowly been adopting features from functional languages:

- Higher-order functions (e.g. map, filter, reduce)
- Futures (a.k.a. Promise)
- Options (a.k.a. Maybe)

To a functional programmer, these are all just examples of *monads*, but to everyone else they have become elegant ways to deal with emerging challenges in software engineering, such as big data processing, concurrency, and avoiding the costly [null reference error](https://www.infoq.com/presentations/Null-References-The-Billion-Dollar-Mistake-Tony-Hoare/).

## Message passing

Going back to I/O, since it is a pesky issue for functional programming... another way to think about I/O is as a function call between two executables.

If you consider your system as an abstract computation, forgetting for a moment the particular technology on which it is built (CPUs, RAM, network interfaces, operating systems, executable files, IPC, etc), the difference between a function call and I/O becomes an implementation detail, an artificial boundary that was drawn to fit the abstract computation to the hardware and software platform. How, then, do we model this interaction in a way that is independent of the implementation?

The answer is *message passing*.

Many things in computing can be modelled as sending a message:

- reading from/writing to memory/disk
- calling a function
- sending an HTTP request

All software can be decomposed into computation and "communication", which forms the glue between the computation. Communication can occur at many different levels, as a result of the memory hierarchy employed by computers -- CPU registers, RAM, disk storage, and networks. "Message passing" is a decent way to model all of these interactions in a uniform way. Which form a particular communication takes is an important choice when mapping an abstract system to a particular technology.

## Software isomorphisms

[They say](https://www.stroustrup.com/quotes.html) that there are only languages that everybody complains about and languages that nobody uses. A common story (and my story more or less) is to start out in C++ / Java / JavaScript, then discover a functional language like Clojure or OCaml (or even Rust), experience the pure bliss of functional programming, and suffer withdrawal forever more at your day job.

[With time](https://en.wikipedia.org/wiki/Gartner_hype_cycle), you realize that you can apply the lessons from functional programming to become a better *software engineer* regardless of your language, and that many features that you miss from functional languages can be implemented (or at least approximated) in other languages. These equivalences are called [software isomorphisms](https://blog.ploeh.dk/2018/01/08/software-design-isomorphisms/), and there are many of them. Arguably the most widely known example is the old saying that *[objects are a poor man's closures](https://people.csail.mit.edu/gregs/ll1-discuss-archive-html/msg03277.html)*.

This point is not meant to defend established programming languages, but rather to help cope with how things are versus how we may wish them to be, and to offer a deeper truth. When you abstract the computation from the technology on which it is implemented (which for us is computer hardware and software), you realize that there are many ways to produce the same result, and your tools, while important and worthy of continual improvement, aren't necessarily worth optimizing at the expense of everything else. By all means, seek the development tools that make you more productive, but remember also that you are not just a *computer programmer*, but an *engineer*. Computer programmers program computers; engineers design and build systems to solve problems. The day-to-day work might look the same, but the difference in perspective, and the wisdom it provides, is massive.

## Negative engineering

Prefect promotes the concept of [negative engineering](https://medium.com/the-prefect-blog/positive-and-negative-data-engineering-a02cb497583d), which is all the code you write to deal with all the things that can go wrong in your computation. Error handling is one of the major aspects by which programming languages are often evaluated and compared. Some examples:

- C returns a null pointer or sets a global error code
- Java, Python, and JavaScript throw exceptions
- Rust, Go, and Zig return errors alongside results

Returning errors seems to be the preferred approach when correctness is a major concern. Throwing and catching errors is convenient when you want to iterate quickly without stopping to deal with every possible error condition, with the obvious downside that it obscures those error conditions from the reader.

A major goal of Prefect, and workflow managers in general, is to streamline and even automate error handling as much as possible. Tasks can be retried and adjusted based on the type of error (e.g. retry with increased memory if the task ran out of memory), or be cascaded if the error is unrecoverable. In other words, these workflow managers provide a declarative DSL for error recovery. It would be interesting to see this idea applied more generally to software engineering, like this Python [retry](https://pypi.org/project/retry/) decorator.

## Visualizing code

TODO: multi-layer dataflow graphs as a way to navigate codebases

## Batching and streaming

TODO:
- advantages of batching vs streaming
- interactive computing as code streaming

## Data science frontends

TODO: some combination of Excel + SQL + Jupyter + Figma could be the ultimate data science tool.

See also:
- Enso
- Hex

See also also:
- [Eve](https://witheve.com/)
- [Glamorous Toolkit](https://gtoolkit.com/)
- [Plain English Programming](https://osmosianplainenglishprogramming.blog/)

## WebAssembly

TODO: WebAssembly could become the universal compiler / interpreter, lightweight alternative to containers and VMs

## Hypermedia

TODO: the promise of hypermedia, HTMX versus frontend frameworks

## Language features that I like

TODO:
- Procedural by default (C++, Python, Rust)
- First-class functions (everyone except C)
- Variables immutable by default (Rust)
- Threads (Java)
- Returning errors with shorthand (Rust, Zig)
- Optional typing (Groovy, Mojo)
- Garbage collection (Java, Go, OCaml)
- Options (Haskell, OCaml, Rust)
- REPL (JavaScript, Python)
- Pipes (Bash, Elixir, Nextflow)
- Return last statement (Groovy, Rust, Scala)
