Dataset for Variable Misuse task of the paper: "Learning to Represent Programs with Graphs", ICLR 2018.

The data from each software project is placed in a different folder along with the licensing information.
Note that some of the projects are used only for training or testing. Each .json.gz graph file contains
a list of graphs.

For each project (folder), you can find:
 - graphs/ containing .json.gz files that contain lists of all the graphs of the project.
 - graphs-{train,valid,test} that contains the train-validation-test split.
 - *-tokens.json.gz that contain all the tokens and trivia (whitespace, comments) of the code.
   This is not useful for learning, but can be useful for debugging.
 - *-typehierarchy.json.gz that contains the type hierarchy information for each of the projects.
 - THIRD_PARTY_NOTICE.txt the license of the respective project.


================ Files that contain graphs ========================
A single problem instance (i.e. a graph) is represented by a JSON dictionary with the following fields:
 - "filename": Source file from which example was taken. [Unneeded for task, used for debugging]
 - "slotTokenIdx": Index of token in the source file that is described by this problem instance. [Unneeded for task, used for debugging]
 - "SlotDummyNode": Node in "ContextGraph" corresponding to the considered slot.
 - "SymbolCandidates": List of type-correct in-scope variables that can be used in the considered slot. Each variable represented by a dictionary in which "SymbolDummyNode" identifies the node in "ContextGraph" corresponding to the candidate, "IsCorrect" marks if the candidate is the correct choice, and "SymbolName" gives the name of the variable candidate [Unneeded for task, used for debugging].
 - "ContextGraph": The actual graph extracted for the problem, already reduced to a subgraph in which all nodes have a maximal distance of 8 from the node corresponding to the considered slot. The graph is given as a dictionary with the following properties:
   * "NodeLabels": Dictionary mapping node ids to their labels (either an actual token or the name of a nonterminal node from the program's AST)
   * "NodeTypes": Dictionary mapping nodes ids to their type (for all nodes for which Roslyn reports a type)
   * "Edges": Dictionary mapping edge types to lists of edges of that type present in the graph. Node that only forward edges are included; the implicit backwards edges can be easily derived.


================== Type Hierarchy files ===========================
These files contain the type lattice of each projects. Lattices are DAGs. The .json contains a dictionary with two fields:
 - "types": Is a list of the names of the types.
 - "outgoingEdges": A list that for each element k in outgoingEdges[i], it implies an edge from types[i]-> types[k]




====================== List of Included Projects ======================
https://github.com/akkadotnet/akka.net
https://github.com/AutoMapper/AutoMapper
https://github.com/dotnet/BenchmarkDotNet
https://github.com/Microsoft/BotBuilder
https://github.com/chocolatey/choco
https://github.com/commandlineparser/commandline
https://github.com/Knagis/CommonMark.NET
https://github.com/StackExchange/Dapper
https://github.com/aspnet/EntityFrameworkCore
https://github.com/Humanizr/Humanizer
https://github.com/QuantConnect/Lean
https://github.com/NancyFx/Nancy
https://github.com/JamesNK/Newtonsoft.Json
https://github.com/ninject/Ninject
https://github.com/NLog/NLog
https://github.com/OpenLiveWriter/OpenLiveWriter
https://github.com/opserver/Opserver
https://github.com/dotnet/orleans
https://github.com/App-vNext/Polly
https://github.com/quartznet/quartznet
https://github.com/restsharp/RestSharp
https://github.com/Reactive-Extensions/Rx.NET
https://github.com/scriptcs/scriptcs
https://github.com/SignalR/SignalR
https://github.com/Wox-launcher/Wox