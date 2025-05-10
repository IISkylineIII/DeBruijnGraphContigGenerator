# DeBruijnGraphContigGenerator

# Description
DeBruijnGraphContigGenerator is a Python script that constructs a De Bruijn graph from a list of k-mers and finds an Eulerian path in the graph to generate contigs. The script first builds a De Bruijn graph by considering the prefixes and suffixes of the k-mers. It then finds an Eulerian path, which is used to assemble the contigs, representing the reconstructed sequence from the given k-mers.

# Functionality
build_debruijn_graph(kmers)
Purpose: Builds a De Bruijn graph from a list of k-mers.

# Approach: Each k-mer is split into a prefix and a suffix, and edges are created between the nodes in the graph. The graph is represented as an adjacency list.

find_eulerian_path(graph)
* Purpose: Finds the Eulerian path in the De Bruijn graph.

# Approach:

* Calculates the in-degree and out-degree of each node.

* Identifies the start and end nodes based on the imbalance in in-degrees and out-degrees.

* Finds and returns the Eulerian path using a stack-based approach.

contigs_from_path(path)
* Purpose: Assembles contigs from the Eulerian path.
* Approach: Uses the Eulerian path to concatenate the nodes and create the contigs.

# Parameters
* kmers (list): A list of k-mers (strings) to be used to construct the De Bruijn graph (e.g., ["ATG", "ATG", "TGT", "TGG", "CAT", "GGA", "GAT", "AGA"]).

# Returns
list: A list of contigs (strings) formed from the Eulerian path.


# Example Usage
```

k_mers = ["ATG", "ATG", "TGT", "TGG", "CAT", "GGA", "GAT", "AGA"]

# Build the De Bruijn graph
debruijn_graph = build_debruijn_graph(k_mers)

# Find the Eulerian path in the graph
eulerian_path = find_eulerian_path(debruijn_graph)

# Generate contigs from the Eulerian path
contigs = contigs_from_path(eulerian_path)

# Print the generated contigs
print("Contigs:", contigs)
```

# Output Example:
Contigs: ['ATG', 'TGG', 'GGA', 'GAT', 'ATG', 'TGT', 'GT']

# Applications
* This script is useful for various bioinformatics applications, including:
* Genome Assembly: The De Bruijn graph and Eulerian path are fundamental in modern genome assembly algorithms, such as short-read assembly.
* Sequence Reconstruction: Helps reconstruct the original sequence from fragmented k-mers in next-generation sequencing (NGS) data.
* Metagenomics: Assists in reconstructing microbial genomes from metagenomic sequencing data.
* Bioinformatics Algorithms: A foundational algorithm in computational biology, applicable in various sequence assembly and alignment tasks.

# Requirements
* Python 3.x
* No external libraries required.

# License
*  This project is licensed under the MIT License – see the LICENSE file for details.





