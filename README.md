# BPS Data Storing Format

BPS is a key-value data storing structure. It allows storing data in several types, even arrays.


## Guides and Documentation

All documentation of BPS can be found [here](https://bps-lib.github.io/). It contains all guides and detailed documentation.


## Specification

- **Comments**: BPS allows one-line comments. Comments start with a hash symbol (`#`). E.g. `# This is a comment`.
- **Keys**: keys can be started with an underscore (`_`) or letter, followed by numbers, lower or upper case letters, and/or underscores.
- **Values**:
  * **Strings**: strings must be in double-quotes. E.g. `"this is a string"`.
  * **Chars**: chars must be in quotes. E.g. `'c'`.
  * **Integers**: e.g. `256`.
  * **Float**: floats can be write `256.`, `256.0` or `256f`.
  * **Double**: e.g. doubles can be write `256.d`, `256.0d` or `256d`.
  * **Boolean**: booleans can be `true` or `false`.
  * **Array**: arrays must be between braces (`[ ]`) separated by comma (`,`). E.g. `[0, 1, 2]`, `['a', 'b', 'c']`, `[[0, 1], [0, 1]]` and so on.

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

# Multidimensional array
multArr2:[
  [0, 1, 2],
  [0, 1, 2],
  [0, 1, 2]
];

# And so on
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

```

## BPS Handle Specification

Below will be described all methods that a BPS Handler must have. The methods can have different names to match with the current programming language collections pattern. For example, the `Add` method can be called `put` in Java.

### BPSFile class

#### Attributes
- `private string Path;`
This attribute contains the path of BPSFile. The method set must normalize the path ensuring this has the extension.

#### Methods

- `public void Save()`
This method will call the method `Save(BPSFile file)` from the `BPS` class passing itself.
- `public string Plain()`
This method will call the method `Plain(BPSFile file)` from the `BPS` class passing itself.
- `public void Add(string key, object value)`
This method will add a new value in `BPSFile`. If the key already exists, the value must be updated.
- `public bool Remove(string key)`
This method will remove a value from `BPSFile`. It will return true if was sucessful or false if the key does not exist.
- `public object Find(string key)`
This method will return the value related to the key. If the key does not exist, it will return null.
- `public int Count()`
This method will count the data amount of `BPSFile`.
- `public void Clear()`
This method will erase all values from the `BPSFile`.
- `public void Contains(string key)`
This method checks if a key exists returning true or false.

### BPS class

#### Methods
- `public static BPSFile Load(string path)`
This method will load a `BPSFile` from disk.
- `public static void Save(BPSFile file)`
This method will save a `BPSFile` on disk.
- `public static BPSFile Parse(string data)`
This method will parse a string representation in BPS notation to a `BPSFile`.
- `public static string Plain(BPSFile file)`
This method will return a string representation of a `BPSFile`.
