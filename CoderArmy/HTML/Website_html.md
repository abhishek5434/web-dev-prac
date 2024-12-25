# Project code
```HTML
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>LearnDSA</title>
</head>

<body>
    <header>
        <h1 style="text-align: center;">Learn DSA for Free From Abhishek</h1>
        <nav style="background-color: rgb(196, 216, 255);">
            <ol>
                <li><a href="#first">C++ introduction</a></li>
                <li><a href="#second">C++ Compiler</a></li>
                <li><a href="#array">Array</a></li>
                <li><a href="#tree">Tree</a></li>
                <li><a href="#graph">Graph</a></li>
            </ol>
        </nav>
    </header>
    <main>
        <!-- Introduction to C++ -->
        <section id="first">
            <h2>Introduction to C++</h2>
            <p>C++is a powerful general-purpose programming language that was developed as an extension of the C
                programming
                language by Bjarne Stroustrup in the early 1980s. C++ is widely used for system/software development,
                game
                development, and applications that require high performance.</p>
            <h3>Features of C++</h3>
            <ul>
                <li>Object-Oriented: C++ supports object-oriented programming (OOP) principles, allowing for the
                    creation of
                    classes and objects. This helps in organizing code and promoting reusability.</li>
                <li>Rich Standard Library: C++ provides a rich set of built-in functions and libraries, which can
                    significantly reduce the development time.</li>
                <li>Performance: C++ offers low-level memory manipulation, allowing developers to optimize
                    performance-critical applications.</li>
                <li>Portability: C++ programs can be compiled and run on various platforms without significant
                    modifications.</li>
                <li>Compatibility with C: C++ is compatible with C, allowing for the integration of existing C code.
                </li>
            </ul>
            <h3>Basic Syntax</h3>
            <pre style="background-color: antiquewhite;">
    <code>
    #include &lt;iostream&gt;

        using namespace std;
         
        int main() {
            cout &lt;&lt; "Hello, World!" &lt;&lt; endl;
             return 0;
            }
        </code>
</pre>
            <ul>
                <li>#include &lt;iostream&gt; This includes the input/output stream library, allowing the use of cout
                    for
                    output and cin for input.</li>
                <li>using namespace std;: This line allows access to the standard library features without prefixing
                    them
                    with std::</li>
                <li>int main(): The entry point of every C++ program.</li>
                <li>cout: Used for outputting data to the console.</li>
                <li>return 0;: Indicates that the program has ended successfully.</li>
            </ul>
            <h3>Applications of C++</h3>
            <ol>
                <li>System Software: C++ is used in developing operating systems and system-level applications.</li>
                <li>Game Development: Many game engines and games are written in C++ due to its performance and control
                    over
                    system resources.</li>
                <li>Embedded Systems: C++ is often used in programming embedded systems for devices like smartphones,
                    appliances, and automotive systems.</li>
                <li>Web Browsers: Many web browsers, like Google Chrome, use C++ for performance-critical components.
                </li>
            </ol>
        </section>
        <!-- C++ Compiler -->
        <section id="second">
            <h2>Online C++ compiler</h2>
            <iframe src="https://onecompiler.com/cpp" height="500" width="100%" frameborder="0"
                title="Online C++ compiler"></iframe>
            <br><br>
        </section>
        <!-- Array -->
        <section id="array">
            <h2>Introduction to Array</h2>
            <h3>What is an Array?</h3>
            <p>An array is a data structure that stores a collection of elements, typically of the same data type.
                Arrays
                are used to store multiple values in a single variable, which allows for efficient data management and
                manipulation.</p>
            <img src="./Arrays.webp" alt="Array image" height="300">
            <h3>Characteristics of Arrays</h3>
            <ul>
                <li>Fixed Size: The size of an array is defined when it is created and cannot be changed.</li>
                <li>Indexed: Each element in an array is accessed using an index, which typically starts from 0.</li>
                <li>Homogeneous Elements: All elements in an array must be of the same data type, such as integers,
                    floats,
                    or strings.</li>
            </ul>
            <h3>Types of Arrays</h3>
            <ol>
                <li>One-Dimensional Arrays: A linear list of elements, where each element can be accessed by a single
                    index
                    <ul>
                        <li>Example: int numbers[5]; (stores 5 integers)</li>
                    </ul>
                </li>
                <li>Multi-Dimensional Arrays: Arrays with more than one dimension, commonly used for matrices and tables
                    <ul>
                        <li>Example: int matrix[3][3]; (a 3x3 matrix of integers)</li>
                    </ul>
                </li>
                <li>Dynamic Arrays: Arrays that can change size during program execution, typically implemented using
                    data
                    structures like lists.
                </li>
            </ol>
            <h2>Tutorial for Array</h2>
            <table>
                <tr>
                    <td>
                        <iframe src="https://www.youtube.com/embed/y3OOaXrFy-Q" height="250" width="400"
                            frameborder="0"></iframe>
                    </td>
                    <td>
                        <iframe src="https://www.youtube.com/embed/H_9MSvTL74g" height="250" width="400"
                            frameborder="0"></iframe>
                    </td>
                    <td>
                        <iframe src="https://www.youtube.com/embed/2Gexv2eld4Y" height="250" width="400"
                            frameborder="0"></iframe>
                    </td>
                </tr>
                <tr>
                    <td>
                        <iframe src="https://www.youtube.com/embed/gGaJJovz" height="250" width="400"
                            frameborder="0"></iframe>
                    </td>
                    <td>
                        <iframe src="https://www.youtube.com/embed/7qINbIQK_J8" height="250" width="400"
                            frameborder="0"></iframe>
                    </td>
                    <td>
                        <iframe src="https://www.youtube.com/embed/0LawAwK5OaI" height="250" width="400"
                            frameborder="0"></iframe>
                    </td>
                </tr>
            </table>
        </section>
        <!-- Tree -->
        <section id="tree">
            <h2>Introduction to Trees</h2>
            <p>A tree is a hierarchical data structure that consists of nodes connected by edges. Each tree has a single
                root node at the top, from which all other nodes branch out. Nodes can have zero or more child nodes,
                and
                each child node can further branch out into more nodes. Trees are commonly used to represent
                hierarchical
                relationships, such as file systems or organizational structures.</p>
            <img src="./Trees.webp" alt="Trees image" height="300">
            <!-- Graph -->
            <h3>Characteristics of Trees</h3>
            <ul>
                <li>Root Node: The topmost node in a tree, which has no parent.</li>
                <li> Child Node: A node that is a descendant of another node.</li>
                <li>Parent Node: A node that has one or more child nodes.</li>
                <li>Leaf Node: A node that has no children.</li>
                <li>Depth: The number of edges from the root node to a specific node.</li>
                <li>Height: The number of edges on the longest path from a node to a leaf.</li>
            </ul>
            <h3>Types of Trees</h3>
            <ol>
                <li>Binary Tree: Each node has at most two children, referred to as the left and right children.</li>
                <li>Binary Search Tree (BST): A binary tree where the left child contains only nodes with values less
                    than
                    the parent node, and the right child contains only nodes with values greater than the parent node.
                </li>
                <li>AVL Tree: A self-balancing binary search tree where the difference in heights between the left and
                    right
                    subtrees is at most one.</li>
                <li>Red-Black Tree: A balanced binary search tree with an additional property that ensures the tree
                    remains
                    balanced during insertions and deletions.</li>
                <li>N-ary Tree: A tree in which a node can have at most N children</li>
            </ol>

            <h3>Applications of Trees</h3>
            <ul>
                <li>Data Storage: Trees are used in databases for indexing data and improving search performance.</li>
                <li>File Systems: Hierarchical file systems use tree structures to organize files and directories.</li>
                <li>Network Routing: Trees are used in routing algorithms to manage and optimize the flow of data across
                    networks.</li>
                <li>Artificial Intelligence: Trees, such as decision trees, are used in AI algorithms for
                    decision-making
                    processes.
                </li>
            </ul>
        </section>
        <!-- Grah -->
        <section id="graph">
            <h2>Introduction to Graphs</h2>
            <p>Artificial Intelligence: Trees, such as decision trees, are used in AI algorithms for decision-making
                processes.</p>
            <img src="./Graphs.webp" alt="Graph image" height="300">
            <h3>Characteristics of Graphs</h3>
            <ul>
                <li>Vertices (Nodes): The fundamental units of a graph, representing entities in the graph.</li>
                <li>Edges: Connections between pairs of vertices, which can be directed (one-way) or undirected
                    (two-way).
                </li>
                <li>Degree: The number of edges connected to a vertex. For directed graphs, a vertex can have an
                    in-degree
                    (number of incoming edges) and an out-degree (number of outgoing edges).</li>
                <li>Path: A sequence of edges that connects a sequence of vertices</li>
                <li>Cycle: A path that starts and ends at the same vertex without repeating any edges.</li>
            </ul>

            <h3>Types of Graphs</h3>
            <ol>
                <li>Directed Graph (Digraph): A graph where the edges have a direction, indicating the relationship
                    flows
                    from one vertex to another.</li>
                <li>Undirected Graph: A graph where the edges do not have a direction, indicating a two-way relationship
                    between vertices.</li>
                <li>Weighted Graph: A graph where each edge has an associated weight or cost, often used to represent
                    distances or costs in a network.</li>
                <li>Unweighted Graph: A graph where all edges are treated equally, without any weights.</li>
                <li>Cyclic Graph: A graph that contains at least one cycle.</li>
                <li>Acyclic Graph: A graph that does not contain any cycles, such as a tree.</li>
            </ol>

            <h3>Applications of Graphs</h3>
            <ol>
                <li>Social Networks: Graphs are used to model relationships and interactions between individuals or
                    entities
                    in social media platforms.</li>
                <li>Transportation Networks: Graphs represent roads, intersections, and routes in transportation
                    systems,
                    helping optimize travel and logistics.</li>
                <li>Web Page Link Analysis: The structure of the web can be represented as a graph, with web pages as
                    vertices and hyperlinks as edges, enabling search engines to analyze and rank pages.</li>
                <li>Network Flow: Graphs are utilized in flow networks to model the flow of resources, such as
                    electricity
                    or data, through a network.</li>
            </ol>
            <h2>Tutorial for Graph</h2>
            <table>
                <tr>
                    <td><iframe src="https://www.youtube.com/embed/gGlfzqPT-hE" frameborder="0" height="200"
                            width="350"></iframe></td>
                    <td><iframe src="https://www.youtube.com/embed/bxbrUGvBCnY" frameborder="0" height="200"
                            width="350"></iframe></td>
                    <td><iframe src="https://www.youtube.com/embed/Vtu7qgF0ksw" frameborder="0" height="200"
                            width="350"></iframe></td>
                </tr>
                <tr>
                    <td><iframe src="https://www.youtube.com/embed/oz1EaP_Bw4s" frameborder="0" height="200"
                            width="350"></iframe></td>
                    <td><iframe src="https://www.youtube.com/embed/2JgYwQ6TZ44" frameborder="0" height="200"
                            width="350"></iframe></td>
                    <td><iframe src="https://www.youtube.com/embed/sPlN86EpjJA" frameborder="0" height="200"
                            width="350"></iframe></td>
                </tr>
            </table>
        </section>
    </main>
    <footer>
        <p>&copy; 2022 My Website. All rights reserved by Abhishek.</p>
    </footer>
</body>

</html>
```
