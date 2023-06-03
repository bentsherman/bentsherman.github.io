# (Towards) 101 Graph Examples

A graph is a set of vertices (a.k.a. "nodes") and a set of vertex pairs (a.k.a. "edges") that denote connections between vertices. You can represent just about anything as a graph. To demonstrate this point, I will keep adding examples to this page until I have 101 examples. Some examples are more useful than others... but all of them are valid graph representations.

## A thing

Any individual thing can be represented as a graph with a single node.

## Nothing

Nothing (a.k.a. the void, the abyss) can be represented as an empty graph (i.e. a graph whose nodes are the empty set).

## Lists

A list is a collection of elements with a particular ordering. It can be represented as a graph with a node for each element and edges connecting each element to the succeeding element in the list.

## Maps

A map is an association between two types of elements; essentially it is a list of key-value pairs. A map can be represented as a bipartite graph, where one partition contains a node for each key and the other partition contains a node for each value, and edges connecting each key to its corresponding value.

## Sets

A set is a collection of distinct elements with no particular ordering. Because a graph consists of a set of nodes and a set of edges, any set can be represented as a graph with no edges and whose nodes are the set. This example may seem circular, and it basically is, but I'm going to count it anyway.

## Trees

A tree is a collection of nodes, where each node has a set of child nodes. Each node may have only one parent node, except for the root node, which has no parent. A tree can be represented as a graph with a node for each tree node and edges connecting each child node to its parent. Basically, a tree is just a graph with no cycles.

## Flowcharts

A flowchart is a diagram that describes how to complete some task through a (potentially non-linear) sequence of steps. Flowcharts typically have many types of steps, including beginning and end states, activities, and decisions. A flowchart can be represented as a graph with a node for each step in the flowchart and edges connecting each step to its immediate successors.

## Class diagrams

In object-oriented programming, a class diagram describes the various data types (classes) and the relationships between them. Some common types of relationships include inheritance, composition, and dependency. A class diagram is just a graph, where classes are nodes and relationships are edges. This example may seem redundant, and it basically is, but I'm going to count it anyway.

## Entity-relationship models

An ER model describes the entity types and relationships that can exist between certain entities for a specific domain of knowledge. Such a model is typically used to define the schema of a relational database. An ER model is just a graph, where entity types are nodes and relationships are edges. This example may seem redundant, and it basically is, but I'm going to count it anyway.

## Electric circuits

A electrical network (a.k.a. electric circuit) is an interconnection of electrical components (batteries, resistors, inductors, capacitors, etc.). These networks range in scale and complexity, from a battery and LED to a regional power grid. Such a network can be represented as a graph with a node for each electrical component and edges between nodes that are directly connected.

## Digital logic circuits

A digital logic circuit is a type of electrical network that uses electrical signals and logic gates to perform computations over discrete values. While digital circuits do form a closed circuit by connecting the underlying transistors to a common voltage/current source, it is common to show only the logic gates and input/output "ports" when depicting a digital circuit. Therefore, a digital circuit can be represented as a graph with a node for each logic gate and edges between gates that are directly connected. Input/output ports can be represented with a different type of node.

## File systems

A file system is a structure for storing data. File systems typically consist of files, which represent individual pieces of data, and directories, which represent groups of files and directories. A file system can be represented as a graph with a node for each file/directory, and edges connecting each directory to each file/directory that it contains.

In other words, a file system is a tree whose nodes can be files or directories, such that only directories can have child nodes.

## World Wide Web

The World Wide Web (a.k.a. the Web) is an information system consisting of web pages that are connected to each other via hyperlinks. The Web can be represented as a graph with a node for each web page and edges connecting each web page to each page to which it links.

## Social networks

A social network is a graph whose nodes are social actors and whose edges are associations between social actors. Social actors can be people or organizations. Associations can denote friendships, business ties, sexual or romantic partnerships, or any other sort of interaction between social actors. An unweighted edge could denote the simple presence or absence of a relationship, whereas a weighted edge might denote the magnitude of a relationship, whether positive or negative.

## Dataflow graphs

A dataflow graph shows the sequence of transformations required to produce some output data from some input data. It can be understood as a generalization of a digital logic circuit -- a dataflow graph could be used to describe any layer of computation, from high-level business processes to operating system tasks to digital logic circuits themselves. As such, a dataflow graph has a node for each transformation and edges for the inputs and outputs of each transformation, with additional nodes for the initial inputs and final outputs.

## Multi-layer dataflow graphs

Any dataflow graph can be abstracted into a single transformation to be used in other dataflow graphs. For example, a digital adder circuit could be one step in some mathematical function, which could be one step in some data analysis program, which could be one step in the decision-making workflow of some company, which could be one step in the flow of goods and services throughout the global economy, which could be one step in the evolution of humankind towards any number of futures ranging from nuclear self-destruction to virtual reality introspection to space exploration to AI transcendence. It's [workflows all the way down](./workflows-all-the-way-down.md).

This complex structure can be represented as a multi-layer graph, where each layer is itself a dataflow graph. Within a particular layer, any node can be expanded to a dataflow graph in the layer underneath. More precisely, it is a tree where each node is a dataflow graph and the node's children are the inner dataflow graphs that can be expanded from the nodes within the parent dataflow graph. As we established earlier, this tree structure is itself a graph.

## Matching questions

A matching question is a test question with two lists of items (e.g. terms and definitions) in some arbitrary order. Each item in one list is paired with one item in the other list, and you must match each pair. The answer to a matching question is just a map, so it has the same graph representation -- one node for each item, and edges connecting each matching pair.

<center>
<img src="http://personal.psu.edu/bxb11/QuizQuestions/media/Matching.png" alt="matching question" width="200px"/>
</center>

## Choose Your Own Adventure stories

Originally inspired by the *Choose Your Own Adventure* book series by Edward Packard, a choose-your-own-adventure story contains points where you must choose one of several paths, and different paths can lead to different endings. Since all of the possible paths must be layed out sequentially when printed as a book, choosing a path usually requires you to jump to a different page each time. A CYOA story can be represented as a graph with a node for each continuous segment in the story and edges connecting each segment to its possible paths.
