# Automatically detect line delimiters in a text file

This helper function was written expressly for
[`set_physical`](https://docs.ropensci.org/EML/reference/set_physical.md)
to be able to automate its `recordDelimiter` argument.

## Usage

``` r
detect_delim(path, nchar = 1000)
```

## Arguments

- path:

  (character) File to search for a delimiter

- nchar:

  (numeric) Maximum number of characters to read from disk when
  searching

## Value

(character) If found, the delimiter, it not, \r\n
