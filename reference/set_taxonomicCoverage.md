# set_taxonomicCoverage

set_taxonomicCoverage

## Usage

``` r
set_taxonomicCoverage(sci_names, expand = FALSE, db = "itis")
```

## Arguments

- sci_names:

  string (space separated) or list or data frame of scientific names for
  species covered.

- expand:

  Set to TRUE to use \`\[taxadb\]\` to expand sci_names into full
  taxonomic classifications

- db:

  The taxonomic database to query (when expand is set to `TRUE`). See
  \`\[taxadb::filter_name\]\` for valid options. Defaults to 'itis'.

## Value

a taxonomicCoverage object for EML

## Details

Turn a data.frame or a list of scientific names into a taxonomicCoverage
block sci_names can be a space-separated character string or a data
frame with column names as rank name or a list of user-defined
taxonomicClassification

## Note

If "sci_names" is a data frame, column names of the data frame are rank
names. For user-defined "sci_names", users must make sure that the order
of rank names they specify is from high to low. Ex.
"Kingdom","Phylum","Class","Order","Family","Genus","Species","Common"
EML permits any rank names provided they go in descending order.

## Examples

``` r

taxon_coverage <- set_taxonomicCoverage("Macrocystis pyrifera")

sci_names <- data.frame(
  Kingdom = "Plantae",
  Phylum = "Phaeophyta",
  Class = "Phaeophyceae",
  Order = "Laminariales",
  Family = "Lessoniaceae",
  Genus = "Macrocystis",
  specificEpithet = "pyrifera"
)
taxon_coverage <- set_taxonomicCoverage(sci_names)

 # Examples that may take > 5s

## use a list of lists for multiple species
sci_names <- list(list(
  Kingdom = "Plantae",
  Phylum = "Phaeophyta",
  Class = "Phaeophyceae",
  Order = "Laminariales",
  Family = "Lessoniaceae",
  Genus = "Macrocystis",
  specificEpithet = "pyrifera"
))
set_taxonomicCoverage(sci_names)
#> $taxonomicClassification
#> $taxonomicClassification[[1]]
#> $taxonomicClassification[[1]]$taxonRankName
#> [1] "Kingdom"
#> 
#> $taxonomicClassification[[1]]$taxonRankValue
#> [1] "Plantae"
#> 
#> $taxonomicClassification[[1]]$taxonomicClassification
#> $taxonomicClassification[[1]]$taxonomicClassification$taxonRankName
#> [1] "Phylum"
#> 
#> $taxonomicClassification[[1]]$taxonomicClassification$taxonRankValue
#> [1] "Phaeophyta"
#> 
#> $taxonomicClassification[[1]]$taxonomicClassification$taxonomicClassification
#> $taxonomicClassification[[1]]$taxonomicClassification$taxonomicClassification$taxonRankName
#> [1] "Class"
#> 
#> $taxonomicClassification[[1]]$taxonomicClassification$taxonomicClassification$taxonRankValue
#> [1] "Phaeophyceae"
#> 
#> $taxonomicClassification[[1]]$taxonomicClassification$taxonomicClassification$taxonomicClassification
#> $taxonomicClassification[[1]]$taxonomicClassification$taxonomicClassification$taxonomicClassification$taxonRankName
#> [1] "Order"
#> 
#> $taxonomicClassification[[1]]$taxonomicClassification$taxonomicClassification$taxonomicClassification$taxonRankValue
#> [1] "Laminariales"
#> 
#> $taxonomicClassification[[1]]$taxonomicClassification$taxonomicClassification$taxonomicClassification$taxonomicClassification
#> $taxonomicClassification[[1]]$taxonomicClassification$taxonomicClassification$taxonomicClassification$taxonomicClassification$taxonRankName
#> [1] "Family"
#> 
#> $taxonomicClassification[[1]]$taxonomicClassification$taxonomicClassification$taxonomicClassification$taxonomicClassification$taxonRankValue
#> [1] "Lessoniaceae"
#> 
#> $taxonomicClassification[[1]]$taxonomicClassification$taxonomicClassification$taxonomicClassification$taxonomicClassification$taxonomicClassification
#> $taxonomicClassification[[1]]$taxonomicClassification$taxonomicClassification$taxonomicClassification$taxonomicClassification$taxonomicClassification$taxonRankName
#> [1] "Genus"
#> 
#> $taxonomicClassification[[1]]$taxonomicClassification$taxonomicClassification$taxonomicClassification$taxonomicClassification$taxonomicClassification$taxonRankValue
#> [1] "Macrocystis"
#> 
#> $taxonomicClassification[[1]]$taxonomicClassification$taxonomicClassification$taxonomicClassification$taxonomicClassification$taxonomicClassification$taxonomicClassification
#> $taxonomicClassification[[1]]$taxonomicClassification$taxonomicClassification$taxonomicClassification$taxonomicClassification$taxonomicClassification$taxonomicClassification$taxonRankName
#> [1] "specificEpithet"
#> 
#> $taxonomicClassification[[1]]$taxonomicClassification$taxonomicClassification$taxonomicClassification$taxonomicClassification$taxonomicClassification$taxonomicClassification$taxonRankValue
#> [1] "pyrifera"
#> 
#> 
#> 
#> 
#> 
#> 
#> 
#> 
#> 

```
