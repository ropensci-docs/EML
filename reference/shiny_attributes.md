# Create/Edit EML attributes

Create/edit EML attributes, custom units, and factors in a shiny
environment.

## Usage

``` r
shiny_attributes(data = NULL, attributes = NULL)
```

## Arguments

- data:

  (data.frame) the data.frame of data that needs an attribute table

- attributes:

  (data.frame) an existing attributes table

## Details

Attributes can be created from scratch using `shiny_attributes()`. Or an
existing attribute table can be edited using
`shiny_attributes(NULL, attributes)`. Or new attributes can be created
from a data table using `shiny_attributes(data, NULL)`. If attributes
are created from a data table, fields such as \`attributeName\` and
\`numberType\` will be automatically completed based on the attributes
within the data table. If both existing attributes and data table are
entered (i.e. `shiny_attributes(data, attributes)`), any automatically
generated fields based attributes within the data table \*\*will not\*\*
override any non-empty fields in the entered attributes

## Examples

``` r
if (FALSE) { # \dontrun{
# from scratch
out <- shiny_attributes(NULL, NULL)

# from data
data <- iris
out <- shiny_attributes(data, NULL)

# from exisiting attributes
file <- system.file("tests", emld::eml_version(),
  "eml-datasetWithAttributelevelMethods.xml",
  package = "emld"
)
eml <- read_eml(file)
x <- eml$dataset$dataTable$attributeList
df <- get_attributes(x, eml)
out <- shiny_attributes(NULL, df$attributes)

# from attributes and data
out <- shiny_attributes(data, df$attributes)
} # }
```
