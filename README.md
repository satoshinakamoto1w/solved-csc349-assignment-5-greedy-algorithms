Download Link: https://assignmentchef.com/product/solved-csc349-assignment-5-greedy-algorithms
<br>
A greedy algorithm is one that assumes it can repeatedly make locally optimal choices, never having to backtrack, always arriving at a globally optimal solution. The greedy approach can be applied to a wide variety of problems, including those that involve graphs.

<strong>Deliverables:</strong>

<strong>GitHub Classroom: </strong><a href="https://classroom.github.com/a/WfTVjKB2">https://classroom.github.com/a/WfTVjKB2</a>

<strong>Required Files:                    </strong>compile.sh, run.sh

<strong>Optional Files:                           </strong>*.py, *.java, *.clj, *.kt, *.js, *.sh

<h1>Part 1: <em><sub>k</sub></em>-Cores</h1>

A <em><sub>k</sub>-core </em>is a maximal connected subgraph within which every vertex has degree at least <em><sub>k</sub></em>. They have applications in graph-based problems as a computationally inexpensive way of approximating the most densely connected regions of a graph. For example, consider the following undirected graph:

All seven vertices in this graph can be found within a <sub>1</sub>-core, since they all have a degree of at least <sub>1</sub>.

However, the <sub>2</sub>-core contains only vertices <em><sub>v</sub></em><sub>0</sub>, <em><sub>v</sub></em><sub>1</sub>, and <em><sub>v</sub></em><sub>2</sub>. Note that although the graph contains a vertex of degree <sub>3 </sub>(as well as one of degree <sub>5</sub>), there is no <sub>3</sub>-core — there is no subgraph within which <em>every </em>vertex has degree <sub>3</sub>. Vertex <em><sub>v</sub></em><sub>2 </sub>has degree <sub>3</sub>, but its neighbor <em><sub>v</sub></em><sub>0</sub>, for example, only has degree <sub>2</sub>. This means that <em><sub>v</sub></em><sub>0 </sub>cannot be in a <sub>3</sub>-core, and without <em><sub>v</sub></em><sub>0</sub>, <em><sub>v</sub></em><sub>2</sub>’s degree falls below <sub>3</sub>.

Perhaps more importantly, from the perspective of a greedy approach, note that the <em><sub>k</sub></em>-cores form a nesting hierarchy of vertices: any vertices in the <em><sub>i</sub></em>-core must necessarily also be in the <sub>(<em>i </em>− 1)</sub>-core, but there can be vertices in the <sub>(<em>i </em>− 1)</sub>-core that are not in the <em><sub>i</sub></em>-core.

In your programming language of choice per Assignment 1, implement a greedy algorithm to compute the <em>k</em>-cores of a graph. Think carefully about what metric your algorithm will be greedy over<a href="#_ftn1" name="_ftnref1"><sup>[1]</sup></a> and what data structures it will use to keep track of that information. You should be able to produce <em>all </em>of the <em><sub>k</sub></em>-cores of a graph in linear <em>O</em><sub>(</sub>|<em><sub>V </sub></em>| <sub>+ </sub>|<em><sub>E</sub></em>|<sub>) </sub>time<sup>2</sup>.

Each input graph will be provided as an <em>edge list</em>: each edge in the graph will be represented by a commaseparated pair of vertex identifiers, indicating an edge between the first vertex and the second.

You may assume that vertex identifiers are contiguous natural numbers — they begin at <sub>0</sub>, and there will be

no “gaps” in the identifiers used. You may also assume that the graph will be simple and will not contain any isolated vertices<sup>3</sup>.

<sup>1</sup>Consider <em>pruning</em>: removing vertices and edges that cannot possibly be part of some solution.

<sup>2</sup>Formatting and printing the cores will naturally require more time.

<sup>3</sup>Since there are no isolated vertices, there are no meaningful <sub>0</sub>-cores; they will always be identical to the <sub>1</sub>-cores.

<h2>Assignment 5 — Greedy Algorithms</h2>

<h3>Fall 2019                                                                                                                                                       Due: Friday, November 1<sup>st</sup></h3>

For example, the above graph could be represented as:

0, 1 0, <a href="#_ftn2" name="_ftnref2"><sup>[2]</sup></a>1, 2 1, 4 1, 5 1, 6 2, 3

Your program must accept as a command line argument the name of a file containing an edge list as described above, then print to stdout the <em><sub>k</sub></em>-cores according to the following format:

<ul>

 <li>Every non-empty <em><sub>k</sub></em>-core must be printed, starting with <em><sub>k </sub></em><sub>= 1</sub>.</li>

 <li>For each value of <em><sub>k</sub></em>, all vertices in such <em><sub>k</sub></em>-core(s) must appear on a single comma-separated line.</li>

 <li>Each line’s vertices must be sorted in ascending order. Note that vertex identifiers are integers, not strings. The lines themselves must be sorted in ascending order by <em><sub>k</sub></em>. For example:</li>

</ul>

&gt;$ ./compile.sh &gt;$ ./run.sh in1.txt Vertices in 1-cores:

0, 1, 2, 3, 4, 5, 6

Vertices in 2-cores:

0, 1, 2

Your program will be tested using diff, so its printed output must match <em>exactly</em>.

<h1>Part 2: Submission</h1>

The following items must be demonstrated in lab on the day of the deadline:

<ul>

 <li>Pseudocode for an efficient greedy algorithm to find the <em><sub>k</sub></em>-cores of an undirected graph.</li>

 <li>A brief description of the locally optimal choices your algorithm greedily makes, together with a brief justification of why it is safe to assume that those choices will lead to a globally optimal<sup>4 </sup>solution. The following files are required and must be pushed to your GitHub Classroom repository by 8pm on the due date:</li>

 <li>compile.sh — A Bash script to compile your submission (even if it does nothing), as specified.</li>

 <li>run.sh — A Bash script to run your submission, as specified.</li>

</ul>

The following files are optional:

<ul>

 <li>*.py, *.java, *.clj, *.kt, *.js, *.sh — The Python, Java, Clojure, Kotlin, Node.js, or Bash source code files of a working program to find <em><sub>k</sub></em>-cores, as specified.</li>

</ul>

Any files other than these will be ignored.

<sup>4</sup>In this problem, the optimized quantity is the <em>size </em>of the <em><sub>k</sub></em>-cores: for correctness, they must be maximal.

Additionally:

<ul>

 <li>On the date before the due date, the grader will be run after 8pm and provides feedback containing only what your program scores. Only submissions made before 8pm are guaranteed to receive feedback. What your program scores on the official run (the due date) is the final score.</li>

 <li>Late submissions made within 24 hours of the deadline receive a .7 multiplier. If you decide to make a late submission, please notify me by sending an email to <a href="/cdn-cgi/l/email-protection" class="__cf_email__" data-cfemail="fa8c949d8f83cbcec9ba999b968a959683d49f9e8f8d938e92">[email protected]</a> both the subject and the body in the format: ”CSC349,late,asgn&lt;i&gt;”, i being the assignment number.</li>

</ul>

3 of 3

<a href="#_ftnref1" name="_ftn1">[1]</a> of 3

<a href="#_ftnref2" name="_ftn2">[2]</a> of 3