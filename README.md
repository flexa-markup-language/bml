# BPS Data Storing Format

## Specification

- **Comments**: BPS allows one-line comments. Comments start with `#`. E.g. `# This is a comment`.
- **Keys**: keys can be started with underscore (`_`) or letter, followed of numbers, lower or upper case letters and/or underscores.
- **Values**:
  * **Strings**: strings should be in double-quotes. E.g. `"this is a string"`.
  * **Chars**: chars should be in quotes. E.g. `'c'`.
  * **Integers**: e.g. `256`.
  * **Float**: floats can be write `256.`, `256.0` or `256f`.
  * **Double**: e.g. doubles can be write `256.0d` or `256d`.
  * **Boolean**: booleans can be `true` or `false`.
  * **Array**: arrays should be between braces (`[ ]`) separated by comma `,`. E.g. `[0, 1, 2]`, `['a', 'b', 'c']`, `[[0, 1], [0, 1]]` and so on.
