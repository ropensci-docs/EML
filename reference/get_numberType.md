# Get EML numberType

returns the EML numberType (either 'real', 'integer', 'whole', or
'natural') of input values

## Usage

``` r
get_numberType(values)
```

## Arguments

- values:

  (numeric/character) a vector of values, if vector is non-numeric will
  return NA

## Value

the numberType of `values` (either 'real', 'integer', 'whole', or
'natural').

## Examples

``` r
if (FALSE) { # \dontrun{
# To get numberType for each column in a data.frame:

unlist(lapply(df, function(x) get_numberType(x)))
} # }
```
