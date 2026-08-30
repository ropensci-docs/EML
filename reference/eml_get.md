# eml_get

eml_get

## Usage

``` r
eml_get(x, element, from = "list", ...)
```

## Arguments

- x:

  an EML object or child/descendant object

- element:

  name of the element to be extracted. If multiple occurrences are
  found, will extract all

- from:

  explicit type for the input format. Possible values: "xml", "json",
  "list", or "guess" with "list" as the default.

- ...:

  additional arguments

## Examples

``` r
# \donttest{
f <- system.file("tests", emld::eml_version(), "eml-datasetWithUnits.xml", package = "emld")
eml <- read_eml(f)
eml_get(eml, "physical")
#> characterEncoding: ASCII
#> dataFormat:
#>   textFormat:
#>     numHeaderLines: '1'
#>     attributeOrientation: column
#>     simpleDelimited:
#>       fieldDelimiter: \t
#> distribution:
#>   online:
#>     url: http://metacat.nceas.ucsb.edu/knb/servlet/metacat?action=read&docid=knb.46.1
#> objectName: CDR LTER-patterns among communities.txt
#> size:
#>   unit: bytes
#>   size: '1245'
eml_get(eml, "attributeList")
#> attribute:
#> - id: att.1
#>   attributeName: fld
#>   attributeLabel: Field
#>   attributeDefinition: "Field where the data was collected\n        "
#>   storageType: string
#>   measurementScale:
#>     nominal:
#>       nonNumericDomain:
#>         id: nd.1
#>         textDomain:
#>           definition: Valid names of fields
#> - id: att.2
#>   attributeName: year
#>   attributeLabel: year
#>   attributeDefinition: "The year the data was collected\n        "
#>   storageType: gYear
#>   measurementScale:
#>     dateTime:
#>       formatString: YYYY
#>       dateTimePrecision: '1'
#>       dateTimeDomain:
#>         id: dd.2
#>         bounds:
#>           minimum:
#>             exclusive: 'false'
#>             minimum: '1944'
#> - id: att.3
#>   attributeName: sr
#>   attributeLabel: Species Richness
#>   attributeDefinition: Species richness for CDR
#>   storageType: float
#>   measurementScale:
#>     interval:
#>       unit:
#>         standardUnit: number
#>       precision: '0.5'
#>       numericDomain:
#>         id: nd.3
#>         numberType: real
#>         bounds:
#>           minimum:
#>             exclusive: 'true'
#>             minimum: '0'
#> - id: att.4
#>   attributeName: pctcov
#>   attributeLabel: percent cover
#>   attributeDefinition: "The percent ground cover on the field\n        "
#>   storageType: float
#>   measurementScale:
#>     ratio:
#>       unit:
#>         standardUnit: dimensionless
#>       precision: '0.1'
#>       numericDomain:
#>         id: nd.4
#>         numberType: real
#>         bounds:
#>           minimum:
#>             exclusive: 'true'
#>             minimum: '0'
#>           maximum:
#>             exclusive: 'true'
#>             maximum: 1e2
#> - id: att.5
#>   attributeName: avesr91
#>   attributeLabel: Average Species Richness for 1991
#>   attributeDefinition: "The average species richness for the field in 1991\n        "
#>   storageType: float
#>   measurementScale:
#>     ratio:
#>       unit:
#>         standardUnit: second
#>       precision: '0.1'
#>       numericDomain:
#>         id: nd.5
#>         numberType: real
#>         bounds:
#>           minimum:
#>             exclusive: 'true'
#>             minimum: '0'
#> - id: att.6
#>   attributeName: avesr92
#>   attributeLabel: Average Species Richness for 1992
#>   attributeDefinition: "The average species richness for the field in 1992\n        "
#>   storageType: float
#>   measurementScale:
#>     ratio:
#>       unit:
#>         standardUnit: cubicFeetPerSecond
#>       precision: '0.1'
#>       numericDomain:
#>         references: nd.5
#> - id: att.7
#>   attributeName: avesr93
#>   attributeLabel: Average Species Richness for 1993
#>   attributeDefinition: "The average species richness for the field in 1993\n        "
#>   storageType: float
#>   measurementScale:
#>     ratio:
#>       unit:
#>         standardUnit: cubicMeter
#>       precision: '0.1'
#>       numericDomain:
#>         references: nd.5
#> - id: att.8
#>   attributeName: avesr94
#>   attributeLabel: Average Species Richness for 1994
#>   attributeDefinition: "The average species richness for the field in 1994\n        "
#>   storageType: float
#>   measurementScale:
#>     ratio:
#>       unit:
#>         standardUnit: radian
#>       precision: '0.1'
#>       numericDomain:
#>         references: nd.5
#> - id: att.9
#>   attributeName: avesr95
#>   attributeLabel: Average Species Richness for 1995
#>   attributeDefinition: "The average species richness for the field in 1995\n        "
#>   storageType: float
#>   measurementScale:
#>     ratio:
#>       unit:
#>         standardUnit: meter
#>       precision: '0.1'
#>       numericDomain:
#>         references: nd.5
#> - id: att.10
#>   attributeName: avesr96
#>   attributeLabel: Average Species Richness for 1996
#>   attributeDefinition: "The average species richness for the field in 1996\n        "
#>   storageType: float
#>   measurementScale:
#>     ratio:
#>       unit:
#>         standardUnit: inch
#>       precision: '0.1'
#>       numericDomain:
#>         references: nd.5
#> - id: att.11
#>   attributeName: MeanSR
#>   attributeLabel: mean species richness
#>   attributeDefinition: "the mean species richness from 1991 to 1996\n        "
#>   storageType: float
#>   measurementScale:
#>     ratio:
#>       unit:
#>         standardUnit: nanogram
#>       precision: '0.1'
#>       numericDomain:
#>         references: nd.5
#> - id: att.12
#>   attributeName: biomass
#>   attributeLabel: Biomass
#>   attributeDefinition: "The total biomass measured in this field\n        "
#>   storageType: float
#>   measurementScale:
#>     ratio:
#>       unit:
#>         customUnit: gramsPerSquareMeter
#>       precision: '0.01'
#>       numericDomain:
#>         id: nd.6
#>         numberType: real
#>         bounds:
#>           minimum:
#>             exclusive: 'true'
#>             minimum: '0'
#> - id: att.13
#>   attributeName: sppm2
#>   attributeLabel: Species Per Square Meter
#>   attributeDefinition: "Calculated species per square meter\n        "
#>   storageType: float
#>   measurementScale:
#>     ratio:
#>       unit:
#>         customUnit: speciesPerSquareMeter
#>       precision: '0.01'
#>       numericDomain:
#>         id: nd.7
#>         numberType: real
#>         bounds:
#>           minimum:
#>             exclusive: 'true'
#>             minimum: '0'
#> - id: att.14
#>   attributeName: time
#>   attributeLabel: Time
#>   attributeDefinition: "The time of day for this observation, 24 hour clock\n        "
#>   storageType: time
#>   measurementScale:
#>     dateTime:
#>       formatString: hh:mm:ss.s
#>       dateTimePrecision: '0.1'
#>       dateTimeDomain:
#>         id: dd.3
#>         bounds:
#>           minimum:
#>             exclusive: 'true'
#>             minimum: '15:00:00.0'
#>           maximum:
#>             exclusive: 'true'
#>             maximum: '19:00:00.0'
#> id: at.1

## The first argument need not be an "eml" class, it could be a child element; e.g.
eml_get(eml$dataset$dataTable, "physical")
#> characterEncoding: ASCII
#> dataFormat:
#>   textFormat:
#>     numHeaderLines: '1'
#>     attributeOrientation: column
#>     simpleDelimited:
#>       fieldDelimiter: \t
#> distribution:
#>   online:
#>     url: http://metacat.nceas.ucsb.edu/knb/servlet/metacat?action=read&docid=knb.46.1
#> objectName: CDR LTER-patterns among communities.txt
#> size:
#>   unit: bytes
#>   size: '1245'
# }
```
