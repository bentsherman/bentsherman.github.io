# Workflows All the Way Down

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

<!--

Imperative vs functional/reactive programming.

Object-oriented vs procedural programming, data-oriented design.

How to navigate an object-oriented codebase (classes as operators, input fields vs intermediate fields, method fragmentation)

Prefect's idea of positive vs negative engineering.

Gradual adoption of ideas from functional programming: maps, filters, reductions, promises, maybe monads.

Future of programming (procedural, functional, Rust)
- software isomorphisms

Different ways to visualize code, multi-layer dataflow graph

To Batch or to Stream
- non-blocking I/O
- Interactive programming environments, batch vs streaming
- Start with batch vs streaming vs interactive in the context of HPC, expand to computing generally.
- Interactive computing is code streaming?

Data science frontends
- Excel + SQL + Jupyter + Figma
- Enso
- Hex

Web Assembly vs containers vs VMs

HTMX vs frontend frameworks

-->
