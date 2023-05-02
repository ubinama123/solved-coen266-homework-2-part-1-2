Download Link: https://assignmentchef.com/product/solved-coen266-homework-2-part-1-2
<br>
PART 1

<strong>Problem 1: </strong>Consider a state space where the start state is number 1 and the successor function for state n returns two states, numbers 2n and 2n + 1.

(a). Draw the portion of the state space for states 1 to 15.

(b). Suppose the goal state is 11. List the order in which nodes will be visited for breadth-first search, depth-limited search with limit 3, and iterative deepening search.

<strong>Problem 2: </strong>(Provide derivations of your answer, that is, draw the search tree, and write down the list of visited nodes and the corresponding frontier nodes). Execute Tree Search through this graph (i.e. do not remember visited nodes). S is the start node, and G is the goal node. Step costs are given next to each arc. Heuristic function values are given in the table on the right. The successors of each node are indicated by the arrows out of that node. Use the alphabetical order as tie-breakers, i.e. if nodes A, B, and C are available to expand, expand A before B, B before C. For each search strategy below, show the order in which nodes are expanded, ending with the goal node that is found. Show the solution path from start to goal, and give the cost of the solution path that is found.

<strong> </strong>

<strong> </strong>

<h1>2.a depth-first search</h1>

Order of node expansion: ____________________________________________________________

Path found: _________________________________   Cost of path found: _____________________ <strong>2.b uniform-cost search </strong>

Order of node expansion: ____________________________________________________________

Path found: _______________________________________   Cost of path found: _______________

<h1>2.c greedy (best-first) search with h(n)</h1>

Order of node expansion: ____________________________________________________________

Path found: ____________________________________   Cost of path found: __________________

<h1>2.d iterative deepening depth-first search</h1>

Order of node expansion: ____________________________________________________________

Path found: _________________________________   Cost of path found: _____________________ <strong>2.e A* search with h(n) </strong>

Order of node expansion: ____________________________________________________________

Path found: __________________________________   Cost of path found: ____________________

<strong> </strong>

<strong>Problem 3: </strong>(Provide derivations of your answer, that is, work on the search tree, write down the list of visited nodes and the corresponding frontier nodes). Consider the search tree below. The two goal states G1 and G2 are indeed the same goal. The numbers on the edges represent step-costs. You also know the following heuristic estimates: h(B→G2) = 9, h(D→G2) =10, h(A→G1)=2, h(C→G1)=1. In what order will A* search visit the nodes? Explain your answer by giving the value of the evaluation function f(n) for those nodes that the algorithm considers. Also give the solution path.

PART 2

<h1>Problem 1: Iterative Deepening</h1>

In the iterativeDeepeningSearch function in search.py, implement an iterative-deepening search algorithm

(iterative deepening depth-limited depth-first <strong>graph search</strong>). You will probably want to make use of the Node class in search.py. Figure 3.17 and Figure 3.18 from the textbook (also given at the end of this document) may help.

<strong>Experiments:</strong> Test your code using:

python pacman.py -l threeByOneMaze -p SearchAgent -a fn=ids python pacman.py -l testMaze -p SearchAgent -a fn=ids python pacman.py -l tinyMaze -p SearchAgent -a fn=ids python pacman.py -l smallMaze -p SearchAgent -a fn=ids  python pacman.py -l mediumMaze -p SearchAgent -a fn=ids  python pacman.py -l bigMaze -p SearchAgent -a fn=ids

A few additional notes:

x       If Pacman moves too slowly for you, try the option –frameTime 0.

x     All of your search functions need to return a list of <em>actions</em> that will lead the agent from the start to the goal. These actions all have to be legal moves (valid directions, no moving through walls).

x                We are implementing <strong>graph search</strong>, not tree search, so IDS might not return the optimal path.

<h1>Problem 2: A* Search</h1>

Implement A* graph search in the empty function aStarSearch in search.py. A* takes a heuristic function as an argument. Heuristics take two arguments: a state in the search problem (the main argument), and the problem itself (for reference information). The nullHeuristic heuristic function in search.py is a trivial example.

You will probably want to make use of the Node class in search.py and the PriorityQueue class in util.py.

You can test your A* implementation on the original problem of finding a path through a maze to a fixed position using the Manhattan distance heuristic (implemented already as manhattanHeuristic in searchAgents.py).

<table width="695">

 <tbody>

  <tr>

   <td rowspan="3" width="10"> </td>

   <td colspan="2" width="685"><strong>Experiments: </strong>

    <table width="61">

     <tbody>

      <tr>

       <td width="61">–frameTi</td>

      </tr>

     </tbody>

    </table>python pacman.py -l tinyMaze -z .5 -p SearchAgent -a fn=astar,heuristic=manhattanHeuristic python pacman.py -l smallMaze -z .5 -p SearchAgent -a fn=astar,heuristic=manhattanHeuristic  python pacman.py -l mediumMaze -z .5 -p SearchAgent -a fn=astar,heuristic=manhattanHeuristic</td>

  </tr>

  <tr>

   <td width="32">


    <table width="31">

     <tbody>

      <tr>

       <td width="31">me 0</td>

      </tr>

     </tbody>

    </table></td>

   <td rowspan="2" width="653">


    <table width="91">

     <tbody>

      <tr>

       <td width="91">–frameTime 0</td>

      </tr>

     </tbody>

    </table>python pacman.py -l bigMaze -z .5 -p SearchAgent -a fn=astar,heuristic=manhattanHeuristic</td>

  </tr>

  <tr>

   <td width="32"> </td>

  </tr>

 </tbody>

</table>

Note: The following (from the textbook) may be helpful for you to implement the Iterative Deepening depthfirst search algorithm.