# is_standardUnit

is_standardUnit

## Usage

``` r
is_standardUnit(x)
```

## Arguments

- x:

  name of unit to check

## Value

TRUE if unit is exact match to the id of a unit in the Standard Units
Table, FALSE otherwise.

## Examples

``` r
is_standardUnit("amperePerMeter") # TRUE
#> [1] TRUE
is_standardUnit("speciesPerSquareMeter") # FALSE
#> [1] FALSE
```
