# Chapter 1: The Role of Algorithms in Computing

## 1.1 Algorithms

What is an algorithm?
* Informally, any well-defined computational procedure that takes some value(s)
    as input and transforms it (them) into some output.
* They are a tool to solve some well-defined computational problem.

Take the example of the sorting problem: You have `n` number of inputs
(a<sub>1</sub> ... a<sub>n</sub>). You want an output such that the input
sequence is now ordered.

An algorithm can also be proven to be correct. It is considered so if, for all
inputs, it halts with the correct output. Incorrect algorithms can be useful if
we can control their error rate. One example is an algorithm for finding large
prime numbers.

What kind of problems can be solved with algorithms?
* Mapping the Human Genome
* Managing internet traffic and finding the most efficient route from one host
    to another.
* Protection of user information in e-commerce applications.
* Efficient allocation of resources in manufacturing.
* Any problem that can be accurately defined.

When creating algorithms to solve problems, it is important to know data
structures and understand their tradeoffs.

There are some very hard problems in computer science called NP-complete
problems. No efficient algorithm has been found to solve them, but it hasn't
been proven that such an algorithm does not exist. Also interesting is that if
an efficient algorithm exists for any NP-complete problem, it proves the existence of an
efficient algorithm for all of them. It's important to be able to identify such
a problem when it exists. Otherwise, you'll be spend a tremendous amount of time
on a wild goose chase.

It is important to design algorithms with parallelism in mind. So we don't melt
our processors.

### Exercises:
* 1.1-1: A real world example that requires sorting is pairing socks out of a
    dryer. An example of computing a convex hull would be building an
    irregularly shaped fence with a minimized perimeter.
* 1.1-2: Other measures of efficiency are memory usage, power consumption. The
    metrics used are highly dependent on use case.
* 1.1-3: A linked list is a fairly common data structure. Its strengths include
    constant time traversal and low memory overhead. Because elements are only
    aware of the next element, getting any particular element takes O(n) time,
    which is not always optimal.
* 1.1-4: Shortest path and the traveling salesman are similar in that they both
    seek to minimize the total distance traveled. However, with the traveling
    salesman problem, this includes traversing all nodes, whereas the shortest
    path only cares about distance.
* 1.1-5: A problem where only the best solution will do is anything involving
    rocket trajectories, or ballistics. "Good enough" typically results in death
    and failure. There are a lot of situations were an approximate solution will
    suffice, such as scheduling trains. If the system is slightly inefficient,
    no one will be seriously inconvenienced.

## 1.2 Algorithms as a technology
Even if computers were infinitely fast and memory was free, it would still be
valuable to study algorithms, as we want to ensure correctness. And in reality,
as fast as computers may be and as cheap as memory is, they are neither
infinitely fast nor free.

Efficiency is a major concern. There are a number of correct algorithms which
vary in efficiency. These implementation differences are more significant than
differences in hardware and software.

Algorithms are as important in modern computing as GUIs, advanced architectures,
fast networking, etc. as many applications are reliant on efficient algorithms
for certain operations. Even the aforementioned systems rely on algorithms.

### Exercises
* 1.2-1: An application that requires algorithmic content is a GPS application.
    They have to calculate the shortest path from one location to another, but
    must consider a multitude of issues, including current traffic and patterns,
    time of day, weather, obstructions, etc. Algorithms used include shortest
    path calculations and heuristics to account for past data.
* 1.2-2: In this case, insertion sort would beat merge sort for 1 &lt; n &lt;
    44.
* 1.2-3: Roughly 14.32.
