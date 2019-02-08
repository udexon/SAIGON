### Graph Machine: A Unified Graph Theoretic Model for Narrow Artificial Intelligence and Artificial General Intelligenec


Yampolskiy (2018) gave a comprehensive review on ...

We introduce the concept of a "graph machine", a graph comprising both data and code, and is therefore capable of evaluating itself, as model of the human mind. In practice, in order for the graph machine to be able to analyze its own code, it needs to be implemented using a homoiconic programming language. We have implemented a version of the reverse Polish notation, similar to the Forth programming language, called 5GL (the Fifth Generation Graph Language, partly as a pun to Forth). We call our graph machine SAIGON (Stack Machine Artificial Intelligence Graph Object Notation), initially as a pun and extension to JavaScript Object Notation.

One of the important breakthroughs in our investigation concerns the application of graph isomorphism to the input and output of a computer program function.

To put it simply, graph isomorphism simply means to compare if two graphs are “similar”. Of these properties, the number of nodes of a graph is the simplest measure of isomorphism. This operation conveniently divides computer program functions into database related and otherwise. In general, database functions increase the number of nodes in a graph (although we may use database functions to delete nodes in a graph, which is trivial). In contrast to this, most data processing functions take in a large array of numbers (represented as nodes of a graph) and transform them into a smaller set of array, thus reducing the number of nodes in the graph. The underlying principle is that we represent the knowledge of an individual human being as a graph, which is one of the most fundamental and flexible constructs in mathematics.

Further, Narrow AI can be categorized as node reducing functions (NF-). Database functions include node adding functions (NF+). We choose the acronyms NF+ instead of NAF for Node Adding Functions to avoid confusion with the acronym of NAI (narrow Artificial Intelligence). Because of the choice of NF+, we use NF- to denote node reducing functions.

If NAI are node reducing functions (NF-), then there have to be node adding functions (NF+) to construct a graph machine that mimics the human mind. Otherwise there will not be functions that can increase the number of nodes in the graph machine, which will cause it to fail, as NF- would have no input data, which are equivalent to large number of nodes, to operate on. 


- Gounding using graph database, integrate Unix file system, program code as database object

We have also identify a fundamental mechanism of "grounding" for the graph machine: a graph database that includes the Unix filesystem, which in turn contains the graph machine itself, as a graph database object. By extension, the graph database will include code and data to capture and process external signals and data. We will include an Android Kotlin camera example to as demonstration.

- Analyze RPN program, homoiconicity, self evaluating, self awareness

The most crucial starting point of the SAIGON project is the reverse Polish notation (5GL) used in its stack machine engine. Its simplicity and homoiconity implies that the code can be analysed by the graph machine itself, making it "self evaluating" and therefore "self aware". We believe the lack of knowledge about homoiconicity amongst programmers and AI researchers today is the primary reason for the bottleneck in AI research.

- Cloudias, easy to learn, everyone can program AI

One last but not least breakthrough of SAIGON is the cloud implementation of SAIGON -- Cloudias (Cloud *Intelligence Artificielle SAIGON*). We believe RPN is perhaps one of simplest programming languages to learn and SAIGON can be implemented easily on any mobile device due to its small footprint. As such, potentially a large number of programmers or non-programmers can contribute to SAIGON/Cloudias, and *own a piece of it*, which is a very important incentive that breaks the monopolies of cloud computing infrastructure owned by supermega tech corporations.

Further, RPN can also serve as a new foundation of mathematics and make learning of mathematics much easier, thus revolutionize it, as has been proven by projects such as HOL Light and SageMath.


Yampolskiy, R. V. (2018). Why We Do Not Evolve Software? Analysis of Evolutionary Algorithms. Evolutionary Bioinformatics, 14, 1176934318815906. https://doi.org/10.1177%2F1176934318815906
