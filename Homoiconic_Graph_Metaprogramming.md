### Beyond Deep Learning: Bootstrapping Artificial General Intelligence with Homoiconic Graph Metaprogramming

\[ [Table of Contents](https://github.com/udexon/SAIGON/blob/master/0_Table_of_Contents.md) \]

Despite recent advances in deep learning, there has been relatively few attempts at Artificial General Intelligence, let alone promising progress towards it. 

We identify two areas in artificial intelligence research that are critical for achieving AGI:

- symbol grounding problem
- metaprogramming

To address these drawbacks, we propose a solution based on graph theory called SAIGON, that encompasses the following components:

- graph database
- homoiconic metaprogramming

The symbol grounding problem concerns mechanisms by which human beings associate meaning to a word. e.g. the sun, "come here", "go there", ... etc. In our humble opinion, there do not seem to be viable and practical theories or proposals to solve this problem. We propose [SAIGON](https://github.com/udexon/SAIGON/blob/master/README.md), a "homoiconic graph machine", with the hope to prove its viability by exhaustive negation, i.e. it is valid if we we cannot find test cases to negate it.

There are essentially two important steps to implement symbol grounding: graph database and metaprogramming. In graph database, an object is related to multiple objects, which in turn are related to multiple objects. Further, the graph database objects must comprise not only pure data, but methods (functions) as well, which is why homoiconic metaprogramming is crucial.

Metaprogramming concerns writing a program that can analyse and modify another program(s). Homoiconicity concerns with a programming language that has the facilities to analyse its own syntax and structure. We focus on stack machine based reverse Polish notation, as we have shown that it can be ported to any known programming language.

In this project, we propose a ["Man in the Mirror"](https://github.com/udexon/SAIGON/blob/master/Man_in_the_Mirror.md) experiment, that involves coding in SAIGON/RPN, that in turn interfaces to Kotlin  OpenCV camera functions on Android devices, to simulate the sensation and thought process of a man (woman) looking at himself (herself) in the mirror.

