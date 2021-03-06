# trace_graph_modeling
This project is used for the modeling of graphs from LTTNG trace data and can be used for root cause analysis purposes. 

Before running the code make sure you have the modules installed such as graphviz(https://graphviz.org/) and networkx(https://networkx.github.io/).

To run the graph_plot_final which is used for simply producing a graph that presents the dependency of each child to its parent use "python3 graph_plot.py mini.txt --threshold 0.2" this creates a dependency graph using the given data file and removes edges where there dependency is less than the threshold which in this case is 20%.

To run the MergeDepGraph which merges two sets of given data into a singular graph with the dependency of each child to its parent use "python3 MergeDepGraph.py mini.txt mini2.txt".

To run the Compare code which compares two sets of merged graphs use "python3 Compare.py mini2Merged.txt miniMerged.txt" which produces a comparison graph of the two given merged graphs. As explained in our paper "The resulting graph uses dotted lined edges for nodes that only appear within the first merged DepGraph and dashed lined edges for nodes that only appear in the second merged DepGraph. For nodes that appear in both merged DepGraphs we use a solid lined edges and assign a colour to said edge. If for example in DepGraph2 there is a large increase of size from DepGraph1 the edge is given a dark red colour. If there is only a small increase of size from DepGraph2 to DepGraph1 a light red colour is assigned. If there is little to no difference between the two merged graphs the edges are grey. If there is a small decrease in size from Depgraph2 to DepGraph1 the edge is coloured a light green. Finally, if there is a large decrease, the edge is coloured a bright green." where DepGraph is a graph that shows weighted dependencies from a child node to its parent via a %.

The data files have been included in the zip with the code for simplicity but also uploaded by themselves within the repository.
