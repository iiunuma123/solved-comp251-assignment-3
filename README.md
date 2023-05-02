Download Link: https://assignmentchef.com/product/solved-comp251-assignment-3
<br>
<h2>. Ford-Fulkerson</h2>

We will implement the Ford-Fulkerson algorithm to calculate the Maximum Flow of a directed weighted graph. Here, you will use the files WGraph.java and FordFulkerson.java, which are available on the course website. Your role will be to complete two methods in the template FordFulkerson.java.

The file WGraph.java is similar to the file that you used in your previous assignment to build graphs. The only differences are the addition of setter and getter methods for the Edges and the addition of the parameters “source” and “destination”. There is also an additional constructor that will allow the creation of a graph cloning a WGraph object. Graphs are encoded using a similar format than the one used in the previous assignment. The only difference is that now the first line corresponds to two integers, separated by one space, that represent the “source” and the “destination” nodes. An example of such file can be found on the course website in the file ff2.txt. These files will be used as an input in the program FordFulkerson.java to initialize the graphs. This graph corresponds to the same graph depicted in [CLRS2009] page 727.

Your task will be to complete the two static methods (fordfulkerson WGraph graph) and pathDFS(Integer source, Integer destination, WGraph graph). The second method pathDFS finds a path via Depth First Search (DFS) between the nodes “source” and “destination” in the “graph”. You must return an ArrayList of Integers with the list of unique nodes belonging to the path found by the DFS. The first element in the list must correspond to the “source” node, the second element in the list must be the second node in the path, and so on until the last element (i.e., the “destination” node) is stored. If the path does not exist, return an empty path. The method fordfulkerson must compute an integer corresponding to the max flow of the “graph”, as well as the graph encoding the assignment associated with this max flow.

Once completed, compile all the java files and run the command line java FordFulkerson ff2.txt. Your program will output a String containing the relevant information. An example of the expected output is available in the file ff2testout.txt. This output keeps the same format than the file used to build the graph; the only difference is that the first line now represents the maximum flow (instead of the “source” and “destination” nodes). The other lines represent the same graph with the weights updated to the values that allow the maximum flow. The file ff226testout.txt represents the answer to the example showed in [CLRS2009] Page 727. You are invited to run other examples of your own to verify that your program is correct.

<h2>2. Bellman-Ford</h2>

We want to implement the Bellman-Ford algorithm for finding the shortest path in a graph where edges can have negative weights. Once again, you will use the object WGraph. Your task is to complete the method BellmanFord(WGraph g, int source) and shortestPath(int destination) in the file BellmanFord.java.

The method BellmanFord takes an object WGraph named g as an input and an integer that indicates the source of the paths. If the input graph g contains a negative cycle, then the method should throw an exception (see template). Otherwise, it will return an object BellmanFord that contains the shortest path estimates (the private array of integers distances), and for each node, its predecessor in the shortest path from the source (the private array of integers predecessors).

The method shortestPath will return the list of nodes as an array of integers along the shortest path from the source to the destination. If this path does not exists, the method should throw an exception (see template). An example input is available in bf1.txt.

<h2>3. Knapsack Problem</h2>

We have seen in class the Knapsack problem and a dynamic programming algorithm. One could define the Knapsack problem as following:

<strong>Definition. </strong>Let <em>n &gt; </em>0 be the number of distinct items and <em>W &gt; </em>0 be the knapsack capacity. For each item <em>i</em>, <em>w<sub>i </sub>&gt; </em>0 denotes the item weight and <em>v<sub>i </sub>&gt; </em>0 denotes its value. The goal is to maximize the total value

<em>n</em>

X

<em>v</em><em>ix</em><em>i i</em>=1

while

<em>n</em>

X

<em>w<sub>i</sub>x<sub>i </sub>≤ W</em>

<em>i</em>=1

where <em>x<sub>i </sub>∈{</em>0<em>,</em>1<em>} </em>for <em>i ∈{</em>1<em>,…,n}</em>.

<strong>Algorithm. </strong>We recall the recursive form of the dynamic programming algorithm. Let <em>OPT</em>(<em>i,w</em>) be the maximum profit subset of items 1<em>,…,i </em>with weight limit <em>w</em>. If <em>OPT </em>does not select the item <em>i</em>, then <em>OPT </em>selects among items <em>{</em>1<em>,…,i−</em>1<em>} </em>with weight limit <em>w</em>. Otherwise, <em>OPT </em>selects among items <em>{</em>1<em>,…,i − </em>1<em>} </em>with weight limit <em>w − w<sub>i</sub></em>.

<table width="556">

 <tbody>

  <tr>

   <td width="492">We could formalize as</td>

   <td width="64"> </td>

  </tr>

  <tr>

   <td width="492">0<em>OPT</em>(<em>i,w</em>) =         <em>OPT</em>(<em>i − </em>1<em>,w</em>)<sup></sup>max<em>{OPT</em>(<em>i − </em>1<em>,w</em>)<em>,v<sub>i </sub></em>+ <em>OPT</em>(<em>i − </em>1<em>,w − w<sub>i</sub></em>)<em>}</em></td>

   <td width="64">if <em>i </em>= 0 if <em>w<sub>i </sub>&gt; w</em>otherwise</td>

  </tr>

 </tbody>

</table>

<h2>Correctness of dynamic programming algorithm (0)</h2>

Usually, a dynamic programming algorithm can be seen as a recursion and proof by induction is one of the easiest way to show its correctness. The structure of a proof by strong induction <strong>for one variable</strong>, say <em>n</em>, contains three parts. First, we define the <strong>Proposition </strong><em>P</em>(<em>n</em>) that we want to prove for the variable <em>n</em>. Next, we show that the proposition holds for <strong>Base case(s)</strong>, such as <em>n </em>= 0<em>,</em>1<em>,… </em>etc. Finally, in the <strong>Inductive step</strong>, we assume that <em>P</em>(<em>n</em>) holds for any value of <em>n </em>strictly smaller than <em>n<sup>0</sup></em>, then we prove that <em>P</em>(<em>n<sup>0</sup></em>) also holds.

Use the proof by strong induction <strong>properly </strong>to show that the algorithm of the Knapsack problem above is correct.

<h2>Bounded Knapsack Problem</h2>

Let us consider a similar problem, in which each item <em>i </em>has <em>c<sub>i </sub>&gt; </em>0 copies (<em>c<sub>i </sub></em>is an integer). Thus, <em>x<sub>i </sub></em>is no longer a binary value, but a non-negative integer at most equal to <em>c<sub>i</sub></em>, 0 <em>≤ x<sub>i </sub>≤ c<sub>i</sub></em>. Modify the dynamic programming algorithm seen at class for this problem.

<strong>Note: </strong>One could consider a new set, in which item <em>i </em>has <em>c<sub>i </sub></em>occurrences. Then, the algorithm seen as class can be applied. However, this could be costly since <em>c<sub>i </sub></em>might be large. Therefore, the algorithm you propose should be different than this one.

<h2>Unbounded Knapsack Problem</h2>

In this question, we consider the case where the quantity of each item is unlimited. Thus, <em>x<sub>i </sub></em>could be any non-negative integer. Provide a dynamic programming algorithm for this problem.