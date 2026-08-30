# set_coverage

set_coverage

## Usage

``` r
set_coverage(
  beginDate = character(),
  endDate = character(),
  date = character(),
  sci_names = character(),
  geographicDescription = character(),
  westBoundingCoordinate = numeric(),
  eastBoundingCoordinate = numeric(),
  northBoundingCoordinate = numeric(),
  southBoundingCoordinate = numeric(),
  altitudeMinimum = numeric(),
  altitudeMaximum = numeric(),
  altitudeUnits = character()
)
```

## Arguments

- beginDate:

  Starting date for temporal coverage range.

- endDate:

  End date for temporal coverage range

- date:

  give a single date, or vector of single dates covered (instead of
  beginDate and endDate)

- sci_names:

  string (space separated) or list or data frame of scientific names for
  species covered. See details

- geographicDescription:

  text string describing the geographic location

- westBoundingCoordinate:

  Decimal longitude for west edge bounding box

- eastBoundingCoordinate:

  Decimal longitude for east edge bounding box

- northBoundingCoordinate:

  Decimal latitude value for north of bounding box

- southBoundingCoordinate:

  Decimal latitude value for south edge of bounding box

- altitudeMinimum:

  minimum altitude covered by the data (optional)

- altitudeMaximum:

  maximum altitude covered by the data (optional)

- altitudeUnits:

  name of the units used to measure altitude, if given

## Value

a coverage object for EML

## Details

set_coverage provides a simple and concise way to specify most common
temporal, taxonomic, and geographic coverage metadata. For certain
studies this will not be well suited, and users will need the more
flexible but more verbose construction using "new()" methods; for
instance, to specify temporal coverage in geological epoch instead of
calendar dates, or to specify taxonomic coverage in terms of other ranks
or identifiers.

## Note

If "sci_names" is a data frame, column names of the data frame are rank
names. For user-defined "sci_names", users must make sure that the order
of rank names they specify is from high to low. Ex.
"Kingdom","Phylum","Class","Order","Family","Genus","Species","Common"

## Examples

``` r
coverage <-
  set_coverage(
    begin = "2012-06-01", end = "2013-12-31",
    sci_names = "Sarracenia purpurea",
    geographicDescription = "California coast, down through Baja, Mexico",
    west = -122.44, east = -117.15,
    north = 37.38, south = 30.00
  )
```
