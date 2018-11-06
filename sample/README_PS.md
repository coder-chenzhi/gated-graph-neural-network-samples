# Introduction
The zip file should be extract by `jar xvf graph-database.zip` command, instead of `unzip graph-database.zip`. More explanation can be found at this [post](https://askubuntu.com/questions/54904/unzip-error-end-of-central-directory-signature-not-found).

# Data schema
Each .gz file under `graph` and `graph-{train/valid/test}` is a list of graphs. These file can be loaded by `json.load()` function.
```
[
    {
    	"filename": str,
    	"slotTokenIdx": int,
    	"SlotDummyNode": int,
    	"SymbolCandidates": [
    		{
	    		"SymbolDummyNode": int,
	      		"SymbolName": str,
	      		"IsCorrect": bool
      		},
      		...
    	],
    	"ContextGraph": {
    		"Edges": {
    			"Child": [],
    			"NextToken": [],
    			"FormalArgName": [],
			    "LastUse": [],
			    "LastLexicalUse": [],
			    "ReturnsTo": [],
			    "LastWrite": []
    		},
    		"NodeLabels": {
    			"id1": str,
    			"id2": str,
    			...
    		},
    		"NodeTypes": {
    			"id1": str,
    			"id2": str,
    			...
    		}

    	}

  	},
  	...
]
```

Below is a sample:
```json
{
  "filename": "src\\CommandLine\\Infrastructure\\ReferenceEqualityComparer.cs",
  "slotTokenIdx": 65,
  "ContextGraph": {
    "Edges": {
      "Child": [
        [4, 5],
        [4, 6],
        [4, 7],
        [4, 8],
        [4, 0],
        [9, 0],
        [10, 11],
        [12, 13],
        [12, 4],
        [14, 15],
        [16, 17],
        [16, 14],
        [16, 18],
        [16, 10],
        [16, 19],
        [20, 16],
        [20, 21],
        [22, 7],
        [23, 24],
        [24, 25],
        [24, 26],
        [27, 28],
        [27, 23],
        [26, 29],
        [30, 31],
        [30, 27]
      ],
      "NextToken": [
        [5, 0],
        [6, 7],
        [7, 8],
        [8, 32],
        [0, 6],
        [10, 19],
        [13, 5],
        [21, 17],
        [14, 18],
        [15, 14],
        [18, 11],
        [17, 15],
        [19, 33],
        [11, 10],
        [23, 25],
        [25, 29],
        [28, 23],
        [31, 28]
      ],
      "FormalArgName": [
        [7, 34],
        [0, 35]
      ],
      "LastUse": [
        [7, 2],
        [1, 14],
        [2, 10],
        [3, 23]
      ],
      "LastLexicalUse": [
        [7, 2],
        [1, 14],
        [2, 10],
        [3, 23]
      ],
      "ReturnsTo": [
        [12, 21]
      ],
      "LastWrite": [
        [1, 14],
        [2, 10],
        [3, 23]
      ]
    },
    "NodeLabels": {
      "0": "<SLOT>",
      "1": "x",
      "2": "y",
      "3": "Default",
      "4": "ArgumentList",
      "5": "(",
      "6": ",",
      "7": "y",
      "8": ")",
      "9": "IdentifierName",
      "10": "y",
      "11": "object",
      "12": "InvocationExpression",
      "13": "ReferenceEquals",
      "14": "x",
      "15": "object",
      "16": "ParameterList",
      "17": "(",
      "18": ",",
      "19": ")",
      "20": "MethodDeclaration",
      "21": "Equals",
      "22": "IdentifierName",
      "23": "Default",
      "24": "EqualsValueClause",
      "25": "=",
      "26": "ObjectCreationExpression",
      "27": "VariableDeclaration",
      "28": "ReferenceEqualityComparer",
      "29": "new",
      "30": "FieldDeclaration",
      "31": "readonly",
      "32": ";",
      "33": "{",
      "34": "objB",
      "35": "objA"
    },
    "NodeTypes": {
      "1": "object",
      "2": "object",
      "3": "CommandLine.Infrastructure.ReferenceEqualityComparer",
      "7": "object",
      "9": "object",
      "10": "object",
      "12": "bool",
      "13": "bool",
      "14": "object",
      "20": "bool",
      "21": "bool",
      "22": "object",
      "23": "CommandLine.Infrastructure.ReferenceEqualityComparer",
      "26": "void",
      "29": "void"
    }
  },
  "SlotDummyNode": 0,
  "SymbolCandidates": [
    {
      "SymbolDummyNode": 1,
      "SymbolName": "x",
      "IsCorrect": true
    },
    {
      "SymbolDummyNode": 2,
      "SymbolName": "y",
      "IsCorrect": false
    },
    {
      "SymbolDummyNode": 3,
      "SymbolName": "Default",
      "IsCorrect": false
    }
  ]
}
```