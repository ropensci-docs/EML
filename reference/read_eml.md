# read_eml

Read an EML file into R as an emld object.

## Usage

``` r
read_eml(x, from = "xml")
```

## Arguments

- x:

  path to an EML file

- from:

  explicit type for the input format. Possible values: "xml", "json",
  "list", or "guess" with "xml" as the default.

## Value

an emld object (list / S3 object)

## Examples

``` r
f <- system.file("extdata", "example.xml", package = "emld")
eml <- read_eml(f)
```
