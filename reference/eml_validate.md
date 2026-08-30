# eml_validate

eml_validate processes an EML document using the XSD schema for the
appropriate version of EML and determines if the document is
schema-valid as defined by the XSD specification

## Usage

``` r
eml_validate(eml, encoding = "UTF-8", schema = NULL)
```

## Arguments

- eml:

  file path, xml_document,

- encoding:

  optional encoding for files, default UTF-8.

- schema:

  path to schema

## Value

Whether the document is valid (logical)

## Note

this function is simply an alias to \`eml_validate\` in \`emld\` package

## Examples

``` r
# \donttest{

f <- system.file("extdata", "example.xml", package = "emld")

## validate file directly from disk:
eml_validate(f)
#> [1] TRUE
#> attr(,"errors")
#> character(0)

## validate an eml object:
eml <- read_eml(f)
eml_validate(eml)
#> [1] TRUE
#> attr(,"errors")
#> character(0)
# }
```
