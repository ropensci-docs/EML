# set_responsibleParty

set_responsibleParty

## Usage

``` r
set_responsibleParty(
  givenName = NULL,
  surName = NULL,
  organizationName = NULL,
  positionName = NULL,
  address = NULL,
  phone = NULL,
  electronicMailAddress = NULL,
  onlineUrl = NULL,
  userId = NULL,
  id = NULL,
  email = NULL
)
```

## Arguments

- givenName:

  individual's given names (list or vector for multiple names). OR a
  person object.

- surName:

  individual name

- organizationName:

  if party is an organization instead of an individual, name for the org

- positionName:

  individual's position, i.e. "Researcher", "Graduate Student",
  "Professor"

- address:

  address object, see \`eml\$address\` to build an address object

- phone:

  individual or organization phone number

- electronicMailAddress:

  email address (alternatively, can use 'email' argument)

- onlineUrl:

  a URL to the homepage of the individual or organization

- userId:

  the user's ID, usually within a particular system (KNB, DataONE)

- id:

  Identifier for this block, ideally an ORCID id (optional)

- email:

  alias for electronicMailAddress

## Value

A emld object for any responsibleParty (e.g. creator, contact, etc)

## Examples

``` r
# Pass in either a person object or separate values to create an individual
carl <- set_responsibleParty(as.person("Carl Boettiger <cboettig@ropensci.org>"))
matt <- set_responsibleParty("Matthew", "Jones", email = "mbjones@nceas.ucsb.edu")

# To create an organization, use the named `organization` argument to
# specify the organization name
my_org <- set_responsibleParty(
  organization = "My Organization",
  email = "contact@example.org"
)
```
