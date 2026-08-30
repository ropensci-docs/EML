# write_eml

write_eml

## Usage

``` r
write_eml(eml, file, namespaces = NULL, ns = "eml", ...)
```

## Arguments

- eml:

  an emld class object

- file:

  file name to write XML.

- namespaces:

  named character vector of additional XML namespaces to use.

- ns:

  root namespace abbreviation

- ...:

  additional arguments to
  [`write_xml`](http://xml2.r-lib.org/reference/write_xml.md)

## Value

If file is not specified, the result is a character string containing
the resulting XML content. Otherwise return silently.

## Examples

``` r
f <- system.file("extdata", "example.xml", package = "emld")
eml <- read_eml(f)
write_eml(eml, "test.xml")
eml_validate("test.xml")
#> [1] TRUE
#> attr(,"errors")
#> character(0)
unlink("test.xml") # clean up
```
