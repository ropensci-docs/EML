# get_unit_id

A function to assist with getting valid EML unit ids (see examples).
Warning: ensure returned unit is equivalent to input unit (for example
"pH" will return "picohenry" which may or may not be equivalent to the
input unit "pH").

## Usage

``` r
get_unit_id(input_units, eml_version = emld::eml_version())
```

## Arguments

- input_units:

  (character\|vector) input units that needs valid EML unit ids

- eml_version:

  (character) the eml schema version desired (there is a change in the
  way eml units are named from eml-2.1.1 to eml-2.2.0)

## Value

(character) A valid EML unit id. If no valid EML unit id can be found,
the function will output a warning, along with a preformatted custom
unit id.

## Examples

``` r
if (FALSE) { # \dontrun{
# The following all return the same id
get_unit_id("kilometersPerSquareSecond")
get_unit_id("kilometerPerSecondSquared")
get_unit_id("Kilometers per seconds squared")
get_unit_id("km/s^2")
get_unit_id("km s-2")
get_unit_id("s-2 /     kilometers-1") # this works but is not advised
} # }
```
