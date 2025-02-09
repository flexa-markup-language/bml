# The FML Data Serialization Language

FML is a data serialization language. It allows to manipulate data in several types.


## Guides and Documentation

All documentation of FML can be found [here](https://flexa-markup-language.github.io/). It contains all guides and detailed documentation.


## Specification

- **Comments**: FML allows one-line comments. Comments start with a hash symbol (`#`). E.g. `# This is a comment`.
- **Keys**: keys can be started with an underscore (`_`) or letter, followed by numbers, lower or upper case letters, and/or underscores.
- **Values**:
  * **Strings**: strings must be in double-quotes. E.g. `"this is a string"`.
  * **Chars**: chars must be in quotes. E.g. `'c'`.
  * **Integers<sup>1</sup>**: e.g. `255`.
  * **Float<sup>1</sup>**: e.g. floats can be write `255.`, `255.0` or `255f`.
  * **Boolean**: booleans can be `true` or `false`.
  * **Array**: arrays must be between braces (`[ ]`) separated by comma (`,`). E.g. `[0, 1, 2]`, `['a', 'b', 'c']`, `[[0, 1], [0, 1]]` and so on.

<sup>1</sup> Some types must be parsed as maximum language precision for that type.

### File in FML Notation

```

# All data types of a FML file.

# Literals
string:"string \"between\" double quotes";
char:'c';
quote_in_char:'\'';

# Numerics
int:10;
float:0.5;

# Booleans
boolTrue:true;
boolFalse:false;

# Vector
stringArr:["yes", "no", "maybe"];
chargArr:['a', 'b', 'c'];
intArr:[0, 1, 2, 10, -5];
floatArr:[0.9, 1.7, -0.2, 1.06, -5.618];
boolArr:[true, false, true];

# Matrix
multArr2:[
  [0, 1, 2],
  [0, 1, 2],
  [0, 1, 2]
];

# Multidimensional array
multArr3:[
  [
    [0, 1, 2],
    [0, 1, 2],
    [0, 1, 2]
  ],
  [
    [0, 1, 2],
    [0, 1, 2],
    [0, 1, 2]
  ],
  [
    [0, 1, 2],
    [0, 1, 2],
    [0, 1, 2]
  ]
];

# Sub-structures
sub_str:
  v1: 10;
  v2: "sub";
;

# Array of sub-structures
stringArr:[
  sub_str:
    v1:10;
    v2:"sub";
  ;,
  sub_str:
    v1:11;
    v2:"sup";
  ;,
  sub_str:
    v1:20;
    v2:"sut";
  ;
];

```

## FML Handle Specification

Below will be described all methods that a FML Handler must have.

### FML class/source file

#### Methods
- `public static Dictionary<string, object> Parse(string data)`
This method will parse a string representation in FML notation to a dictionary.
- `public static string Stringify(Dictionary<string, object> data)`
This method will return a string representation in FML notation.
