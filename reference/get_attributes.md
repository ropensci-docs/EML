# get_attributes

get_attributes

## Usage

``` r
get_attributes(x, eml = NULL)
```

## Arguments

- x:

  an "attributeList" element from an emld object

- eml:

  The full eml document, needed only if \<references\> outside of
  attributes must be resolved.

## Value

a data frame whose rows are the attributes (names of each column in the
data file) and whose columns describe metadata about those attributes.
By default separate tables are given for each type

## Details

EML metadata can use "references" elements which allow one attribute to
use metadata declared elsewhere in the document. This function will
automatically resolve these references and thus infer the correct
metadata.

## Examples

``` r
f <- system.file("tests", emld::eml_version(), 
  "eml-datasetWithAttributelevelMethods.xml", package = "emld")
eml <- read_eml(f)
get_attributes(eml$dataset$dataTable$attributeList)
#> New names:
#> • `id` -> `id...1`
#> • `id` -> `id...6`
#> New names:
#> • `id` -> `id...1`
#> • `id` -> `id...8`
#> New names:
#> • `id` -> `id...1`
#> • `id` -> `id...8`
#> New names:
#> • `id` -> `id...1`
#> • `id` -> `id...8`
#> • `exclusive` -> `exclusive...10`
#> • `exclusive` -> `exclusive...12`
#> New names:
#> • `id` -> `id...1`
#> • `id` -> `id...8`
#> New names:
#> • `id` -> `id...1`
#> • `id` -> `id...8`
#> • `exclusive` -> `exclusive...9`
#> • `exclusive` -> `exclusive...11`
#> $attributes
#>    id...1 attributeName                    attributeLabel
#> 1   att.1           fld                             Field
#> 2   att.2          year                              year
#> 3   att.3            sr                  Species Richness
#> 4   att.4        pctcov                     percent cover
#> 5   att.5       avesr91 Average Species Richness for 1991
#> 6    <NA>       avesr92 Average Species Richness for 1992
#> 7    <NA>       avesr93 Average Species Richness for 1993
#> 8    <NA>       avesr94 Average Species Richness for 1994
#> 9    <NA>       avesr95 Average Species Richness for 1995
#> 10   <NA>       avesr96 Average Species Richness for 1996
#> 11   <NA>        MeanSR             mean species richness
#> 12 att.14          time                              Time
#>                                              attributeDefinition storageType
#> 1                   Field where the data was collected\n              string
#> 2                      The year the data was collected\n               gYear
#> 3                                       Species richness for CDR       float
#> 4                The percent ground cover on the field\n               float
#> 5   The average species richness for the field in 1991\n               float
#> 6   The average species richness for the field in 1992\n               float
#> 7   The average species richness for the field in 1993\n               float
#> 8   The average species richness for the field in 1994\n               float
#> 9   The average species richness for the field in 1995\n               float
#> 10  The average species richness for the field in 1996\n               float
#> 11         the mean species richness from 1991 to 1996\n               float
#> 12 The time of day for this observation, 24 hour clock\n                time
#>    id...6            definition measurementScale         domain formatString
#> 1    nd.1 Valid names of fields          nominal     textDomain         <NA>
#> 2    <NA>                  <NA>         dateTime dateTimeDomain         YYYY
#> 3    <NA>                  <NA>         interval  numericDomain         <NA>
#> 4    <NA>                  <NA>            ratio  numericDomain         <NA>
#> 5    <NA>                  <NA>            ratio  numericDomain         <NA>
#> 6    <NA>                  <NA>            ratio  numericDomain         <NA>
#> 7    <NA>                  <NA>            ratio  numericDomain         <NA>
#> 8    <NA>                  <NA>            ratio  numericDomain         <NA>
#> 9    <NA>                  <NA>            ratio  numericDomain         <NA>
#> 10   <NA>                  <NA>            ratio  numericDomain         <NA>
#> 11   <NA>                  <NA>            ratio  numericDomain         <NA>
#> 12   <NA>                  <NA>         dateTime dateTimeDomain   hh:mm:ss.s
#>    dateTimePrecision id...8    minimum          unit precision numberType
#> 1               <NA>   <NA>       <NA>          <NA>      <NA>       <NA>
#> 2                  1   dd.2       1944          <NA>      <NA>       <NA>
#> 3               <NA>   nd.3          0 dimensionless       0.5       real
#> 4               <NA>   nd.4          0 dimensionless       0.1       real
#> 5               <NA>   nd.5          0 dimensionless       0.1       real
#> 6               <NA>   <NA>       <NA> dimensionless       0.1       <NA>
#> 7               <NA>   <NA>       <NA> dimensionless       0.1       <NA>
#> 8               <NA>   <NA>       <NA> dimensionless       0.1       <NA>
#> 9               <NA>   <NA>       <NA> dimensionless       0.1       <NA>
#> 10              <NA>   <NA>       <NA> dimensionless       0.1       <NA>
#> 11              <NA>   <NA>       <NA> dimensionless       0.1       <NA>
#> 12               0.1   dd.3 15:00:00.0          <NA>      <NA>       <NA>
#>    exclusive...10 exclusive...12    maximum     id exclusive...9 exclusive...11
#> 1            <NA>           <NA>       <NA>   <NA>          <NA>           <NA>
#> 2            <NA>           <NA>       <NA>   <NA>          <NA>           <NA>
#> 3            <NA>           <NA>       <NA>   <NA>          <NA>           <NA>
#> 4            true           true        100   <NA>          <NA>           <NA>
#> 5            <NA>           <NA>       <NA>   <NA>          <NA>           <NA>
#> 6            <NA>           <NA>       <NA>  att.6          <NA>           <NA>
#> 7            <NA>           <NA>       <NA>  att.7          <NA>           <NA>
#> 8            <NA>           <NA>       <NA>  att.8          <NA>           <NA>
#> 9            <NA>           <NA>       <NA>  att.9          <NA>           <NA>
#> 10           <NA>           <NA>       <NA> att.10          <NA>           <NA>
#> 11           <NA>           <NA>       <NA> att.11          <NA>           <NA>
#> 12           <NA>           <NA> 19:00:00.0   <NA>          true           true
#> 
#> $factors
#> NULL
#> 
```
