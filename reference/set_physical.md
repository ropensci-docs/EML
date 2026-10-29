# set_physical

Will calculate the file size, checksum, and checksum authentication
method algorithm automatically if the argument `objectName` is a file
that exists.

## Usage

``` r
set_physical(
  objectName,
  id = character(),
  numHeaderLines = character(),
  numFooterLines = character(),
  recordDelimiter = detect_delim(objectName),
  fieldDelimiter = ",",
  collapseDelimiters = logical(),
  literalCharacter = character(),
  quoteCharacter = character(),
  attributeOrientation = "column",
  size = NULL,
  sizeUnit = "bytes",
  authentication = NULL,
  authMethod = NULL,
  characterEncoding = character(),
  encodingMethod = character(),
  compressionMethod = character(),
  url = character()
)
```

## Arguments

- objectName:

  name for the object, usually a filename like "hf205-1.csv"

- id:

  optional, an id value for the \<physical\> element in EML, for use in
  referencing

- numHeaderLines:

  Number of header lines preceding data. Lines are determined by the
  physicalLineDelimiter, or if it is absent, by the recordDelimiter.
  This value indicated the number of header lines that should be skipped
  before starting to parse the data.

- numFooterLines:

  Number of footer lines following data. Lines are determined by the
  physicalLineDelimiter, or if it is absent, by the recordDelimiter.
  This value indicated the number of footer lines that should be skipped
  after parsing the data. If this value is omitted, parsers should
  assume the data continues to the end of the data stream.

- recordDelimiter:

  This element specifies the record delimiter character when the format
  is text. The record delimiter is usually a linefeed (\n) on UNIX, a
  carriage return (\r) on MacOS, or both (\r\n) on Windows/DOS.
  Multiline records are usually delimited with two line ending
  characters, for example on UNIX it would be two linefeed characters
  (\n\n). As record delimiters are often non-printing characters, one
  can use either the special value "\n" to represent a linefeed (ASCII
  0x0a) and "\r" to represent a carriage return (ASCII 0x0d).
  Alternatively, one can use the hex value to represent character values
  (e.g., 0x0a).

- fieldDelimiter:

  "," character by default (for csv files). This element specifies a
  character to be used in the object for indicating the ending column
  for an attribute. The delimiter character itself is not part of the
  attribute value, but rather is present in the column following the
  last character of the value. Typical delimiter characters include
  commas, tabs, spaces, and semicolons. The only time the fieldDelimiter
  character is not interpreted as a delimiter is if it is contained in a
  quoted string (see quoteCharacter) or is immediately preceded by a
  literalCharacter. Non-printable quote characters can be provided as
  their hex values, and for tab characters by its ASCII string "\t".
  Processors should assume that the field starts in the column following
  the previous field if the previous field was fixed, or in the column
  following the delimiter from the previous field if the previous field
  was delimited.

- collapseDelimiters:

  The collapseDelimiters element specifies whether sequential delimiters
  should be treated as a single delimiter or multiple delimiters. An
  example is when a space delimiter is used; often there may be several
  repeated spaces that should be treated as a single delimiter, but not
  always. The valid values are yes or no. If it is set to yes, then
  consecutive delimiters will be collapsed to one. If set to no or
  absent, then consecutive delimiters will be treated as separate
  delimiters. Default behavior is no; hence, consecutive delimiters will
  be treated as separate delimiters, by default.

- literalCharacter:

  This element specifies a character to be used for escaping special
  character values so that they are treated as literal values. This
  allows "escaping" for special characters like quotes, commas, and
  spaces when they are intended to be used in an attribute value rather
  than being intended as a delimiter. The literalCharacter is typically
  a \\

- quoteCharacter:

  This element specifies a character to be used in the object for
  quoting values so that field delimiters can be used within the value.
  This basically allows delimiter "escaping". The quoteChacter is
  typically a " or '. When a processor encounters a quote character, it
  should not interpret any following characters as a delimiter until a
  matching quote character has been encountered (i.e., quotes come in
  pairs). It is an error to not provide a closing quote before the
  record ends. Non-printable quote characters can be provided as their
  hex values.

- attributeOrientation:

  Specifies whether the attributes described in the physical stream are
  found in columns or rows. The valid values are column or row. If set
  to 'column', then the attributes are in columns. If set to 'row', then
  the attributes are in rows. Row orientation is rare.

- size:

  This element contains information of the physical size of the entity,
  by default represented in bytes unless the sizeUnit attribute is
  provided to change the units.

- sizeUnit:

  the unit in which size is measured; default is 'bytes'

- authentication:

  This element describes authentication procedures or techniques,
  typically by giving a checksum value for the object. The method used
  to compute the authentication value (e.g., MD5) is listed in the
  method attribute.

- authMethod:

  the method for authentication checksum, e.g. MD5

- characterEncoding:

  This element contains the name of the character encoding. This is
  typically ASCII or UTF-8, or one of the other common encodings.

- encodingMethod:

  This element lists a encoding method used to encode the object, such
  as base64, BinHex.

- compressionMethod:

  This element lists a compression method used to compress the object,
  such as zip, compress, etc. Compression and encoding methods must be
  listed in the order in which they were applied, so that decompression
  and decoding should occur in the reverse order of the listing. For
  example, if a file is compressed using zip and then encoded using MIME
  base64, the compression method would be listed first and the encoding
  method second.

- url:

  optional. The complete url from which the data file can be downloaded,
  if possible.

## Value

an EML physical object, such as used in a dataTable element to define
the format of the data file.

## Examples

``` r
set_physical("hf205-01-TPexp1.csv")
#> $objectName
#> [1] "hf205-01-TPexp1.csv"
#> 
#> $size
#> NULL
#> 
#> $authentication
#> $authentication$authentication
#> NULL
#> 
#> $authentication$method
#> NULL
#> 
#> 
#> $compressionMethod
#> character(0)
#> 
#> $encodingMethod
#> character(0)
#> 
#> $characterEncoding
#> character(0)
#> 
#> $dataFormat
#> $dataFormat$textFormat
#> $dataFormat$textFormat$numHeaderLines
#> character(0)
#> 
#> $dataFormat$textFormat$numFooterLines
#> character(0)
#> 
#> $dataFormat$textFormat$recordDelimiter
#> [1] "\r\n"
#> 
#> $dataFormat$textFormat$attributeOrientation
#> [1] "column"
#> 
#> $dataFormat$textFormat$simpleDelimited
#> $dataFormat$textFormat$simpleDelimited$fieldDelimiter
#> [1] ","
#> 
#> $dataFormat$textFormat$simpleDelimited$collapseDelimiters
#> character(0)
#> 
#> $dataFormat$textFormat$simpleDelimited$quoteCharacter
#> character(0)
#> 
#> $dataFormat$textFormat$simpleDelimited$literalCharacter
#> character(0)
#> 
#> 
#> 
#> 
#> $id
#> character(0)
#> 
#> $distribution
#> list()
#> 
# FIXME set recordDelimiter based on user's system?
# FIXME richer distribution options? use set_distribution at top level?
```
