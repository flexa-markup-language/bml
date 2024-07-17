# The BPS Data Serialization Language

BPS is a key-value data handling structure. It allows to manipulate data in several types, even arrays.


## Guides and Documentation

All documentation of BPS can be found [here](https://bps-lib.github.io/). It contains all guides and detailed documentation.


## Specification

- **Comments**: BPS allows one-line comments. Comments start with a hash symbol (`#`). E.g. `# This is a comment`.
- **Keys**: keys can be started with an underscore (`_`) or letter, followed by numbers, lower or upper case letters, and/or underscores.
- **Values**:
  * **Strings**: strings must be in double-quotes. E.g. `"this is a string"`.
  * **Chars**: chars must be in quotes. E.g. `'c'`.
  * **Integers<sup>1</sup>**: e.g. `255`.
  * **Float<sup>1</sup>**: e.g. floats can be write `255.`, `255.0` or `255f`.
  * **Boolean**: booleans can be `true` or `false`.
  * **Array**: arrays must be between braces (`[ ]`) separated by comma (`,`). E.g. `[0, 1, 2]`, `['a', 'b', 'c']`, `[[0, 1], [0, 1]]` and so on.

<sup>1</sup> Some types must be parsed as maximum language precision for that type.

### File in BPS Notation

```

# All data types of a BPS file.

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

```

## BPS Handle Specification

Below will be described all methods that a BPS Handler must have.

### BPS class

#### Methods
- `public static Dictionary<string, object> Parse(string data)`
This method will parse a string representation in BPS notation to a dictionary.
- `public static string Plain(Dictionary<string, object> data)`
This method will return a string representation in BPS notation.
