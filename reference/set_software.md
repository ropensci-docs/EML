# set_software

set_software

## Usage

``` r
set_software(codemeta)
```

## Arguments

- codemeta:

  codemeta object, see examples

## Value

an eml software element

## Examples

``` r
cm <- jsonlite::read_json(system.file("extdata/codemeta.json", package = "EML"))
software <- set_software(cm)
my_eml <- eml$eml(packageId = "eml-1.2", system = "knb", software = software)

# write_eml(my_eml, "test.xml")
```
