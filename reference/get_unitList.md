# get_unitList

get_unitList

## Usage

``` r
get_unitList(x = NULL)
```

## Arguments

- x:

  an emld object

## Value

a list with two data.frames: "units", a table defining unit names,
types, and conversions to SI, and "unitTypes", defining the type of
unit. For instance, the unit table could define "Hertz" as a unit of
unitType frequency, and the unitType define frequency as a type whose
dimension is 1/time.

## Details

If no unitList is provided, the function reads in the eml-unitDictionary
defining all standard units and unitTypes. This provides a convenient
way to look up standard units and their EML-recognized names when
defining metadata, e.g. in the table passed to \`set_attributes()\`.

## Examples

``` r

# Read in additional units defined in a EML file
# \donttest{
f <- system.file("tests", emld::eml_version(),
  "eml-datasetWithUnits.xml",
  package = "emld"
)
eml <- read_eml(f)
unitList <- get_unitList(eml)

## Read in the definitions of standard units:
get_unitList()
#> $units
#>                                                        id
#> 1                                           dimensionless
#> 2                                                  second
#> 3                                                   meter
#> 4                                                kilogram
#> 5                                                  kelvin
#> 6                                                 coulomb
#> 7                                                  ampere
#> 8                                                    mole
#> 9                                                 candela
#> 10                                                 number
#> 11                                             cubicMeter
#> 12                                          nominalMinute
#> 13                                            nominalHour
#> 14                                             nominalDay
#> 15                                            nominalWeek
#> 16                                            nominalYear
#> 17                                        nominalLeapYear
#> 18                                               nanogram
#> 19                                              microgram
#> 20                                              milligram
#> 21                                              centigram
#> 22                                               decigram
#> 23                                                   gram
#> 24                                               dekagram
#> 25                                              hectogram
#> 26                                               megagram
#> 27                                                  tonne
#> 28                                                  pound
#> 29                                                    ton
#> 30                                                celsius
#> 31                                             fahrenheit
#> 32                                              nanometer
#> 33                                             micrometer
#> 34                                                 micron
#> 35                                             millimeter
#> 36                                             centimeter
#> 37                                              decimeter
#> 38                                              dekameter
#> 39                                             hectometer
#> 40                                              kilometer
#> 41                                              megameter
#> 42                                               angstrom
#> 43                                                   inch
#> 44                                                Foot_US
#> 45                                                   foot
#> 46                                        Foot_Gold_Coast
#> 47                                                 fathom
#> 48                                           nauticalMile
#> 49                                                   yard
#> 50                                            Yard_Indian
#> 51                                            Link_Clarke
#> 52                                             Yard_Sears
#> 53                                                   mile
#> 54                                             nanosecond
#> 55                                            microsecond
#> 56                                            millisecond
#> 57                                            centisecond
#> 58                                             decisecond
#> 59                                             dekasecond
#> 60                                            hectosecond
#> 61                                             kilosecond
#> 62                                             megasecond
#> 63                                                 minute
#> 64                                                   hour
#> 65                                              kiloliter
#> 66                                             microliter
#> 67                                             milliliter
#> 68                                                  liter
#> 69                                                 gallon
#> 70                                                  quart
#> 71                                                 bushel
#> 72                                              cubicInch
#> 73                                                   pint
#> 74                                             meterCubed
#> 75                                        centimeterCubed
#> 76                                              inchCubed
#> 77                                                 radian
#> 78                                                 degree
#> 79                                                   grad
#> 80                                              steradian
#> 81                                              megahertz
#> 82                                              kilohertz
#> 83                                                  hertz
#> 84                                             millihertz
#> 85                                                 newton
#> 86                                                  joule
#> 87                                                calorie
#> 88                                     britishThermalUnit
#> 89                                              footPound
#> 90                                                langley
#> 91                                                  lumen
#> 92                                                    lux
#> 93                                              becquerel
#> 94                                                   gray
#> 95                                                sievert
#> 96                                                  katal
#> 97                                                  henry
#> 98                                               megawatt
#> 99                                               kilowatt
#> 100                                                  watt
#> 101                                             milliwatt
#> 102                                              megavolt
#> 103                                              kilovolt
#> 104                                                  volt
#> 105                                             millivolt
#> 106                                                 farad
#> 107                                                   ohm
#> 108                                              ohmMeter
#> 109                                       siemensPerMeter
#> 110                                  siemensPerCentimeter
#> 111                                                siemen
#> 112                                               siemens
#> 113                                                 weber
#> 114                                                 tesla
#> 115                                                pascal
#> 116                                            megapascal
#> 117                                            kilopascal
#> 118                                           hectopascal
#> 119                                            atmosphere
#> 120                                                   bar
#> 121                                              millibar
#> 122                                               decibar
#> 123                               kilogramsPerSquareMeter
#> 124                                   gramsPerSquareMeter
#> 125                              milligramsPerSquareMeter
#> 126                                   kilogramsPerHectare
#> 127                                       tonnePerHectare
#> 128                                   poundsPerSquareInch
#> 129                              gramPercentimeterSquared
#> 130                                   gramPerMeterSquared
#> 131                                    kilogramPerHectare
#> 132                               kilogramPerMeterSquared
#> 133                              milligramPerMeterSquared
#> 134                                          poundPerAcre
#> 135                                   poundPerInchSquared
#> 136                                 kilogramPerCubicMeter
#> 137                               milliGramsPerMilliLiter
#> 138                                         gramsPerLiter
#> 139                               milligramsPerCubicMeter
#> 140                                    microgramsPerLiter
#> 141                                    milligramsPerLiter
#> 142                               gramsPerCubicCentimeter
#> 143                                    gramsPerMilliliter
#> 144                                gramPerCentimeterCubed
#> 145                                          gramPerLiter
#> 146                                     gramPerMilliliter
#> 147                                     microgramPerLiter
#> 148                                     milligramPerLiter
#> 149                                milligramPerMeterCubed
#> 150                                 kilogramPerMeterCubed
#> 151                                 megagramPerMeterCubed
#> 152                                milligramPerMilliliter
#> 153                                   gramsPerLiterPerDay
#> 154                          milligramPerMeterCubedPerDay
#> 155                                    gramPerDayPerLiter
#> 156                                       litersPerSecond
#> 157                                  cubicMetersPerSecond
#> 158                                    cubicFeetPerSecond
#> 159                                    footCubedPerSecond
#> 160                                        literPerSecond
#> 161                                   meterCubedPerSecond
#> 162                                           squareMeter
#> 163                                                   are
#> 164                                               hectare
#> 165                                      squareKilometers
#> 166                                     squareMillimeters
#> 167                                     squareCentimeters
#> 168                                                  acre
#> 169                                            squareFoot
#> 170                                            squareYard
#> 171                                            squareMile
#> 172                                     centimeterSquared
#> 173                                           footSquared
#> 174                                      kilometerSquared
#> 175                                          meterSquared
#> 176                                           mileSquared
#> 177                                     millimeterSquared
#> 178                                           yardSquared
#> 179                                  litersPerSquareMeter
#> 180                                        bushelsPerAcre
#> 181                                      litersPerHectare
#> 182                                         bushelPerAcre
#> 183                                       literPerHectare
#> 184                                  literPerMeterSquared
#> 185                                  meterCubedPerHectare
#> 186                             meterCubedPerMeterSquared
#> 187                                meterSquaredPerHectare
#> 188                                squareMeterPerKilogram
#> 189                               meterSquaredPerKilogram
#> 190                                       metersPerSecond
#> 191                                          metersPerDay
#> 192                                            feetPerDay
#> 193                                         feetPerSecond
#> 194                                           feetPerHour
#> 195                                        yardsPerSecond
#> 196                                          milesPerHour
#> 197                                        milesPerSecond
#> 198                                        milesPerMinute
#> 199                                  centimetersPerSecond
#> 200                                  millimetersPerSecond
#> 201                                     centimeterPerYear
#> 202                                                 knots
#> 203                                     kilometersPerHour
#> 204                                   centimeterPerSecond
#> 205                                            footPerDay
#> 206                                           footPerHour
#> 207                                         footPerSecond
#> 208                                           inchPerHour
#> 209                                      kilometerPerHour
#> 210                                                  knot
#> 211                                           meterPerDay
#> 212                                        meterPerSecond
#> 213                                           milePerHour
#> 214                                         milePerMinute
#> 215                                         milePerSecond
#> 216                                      millimeterPerDay
#> 217                                   millimeterPerSecond
#> 218                                         yardPerSecond
#> 219                                metersPerSecondSquared
#> 220                                 meterPerSecondSquared
#> 221                                            waveNumber
#> 222                                          inverseMeter
#> 223                                     inverseCentimeter
#> 224                                 cubicMeterPerKilogram
#> 225                               cubicMicrometersPerGram
#> 226                                 meterCubedPerKilogram
#> 227                                micrometerCubedPerGram
#> 228                                  amperePerSquareMeter
#> 229                                 amperePerMeterSquared
#> 230                                        amperePerMeter
#> 231                                     molePerCubicMeter
#> 232                                              molarity
#> 233                                     molePerMeterCubed
#> 234                                          molePerLiter
#> 235                                     millimolePerLiter
#> 236                                     micromolePerLiter
#> 237                                      nanomolePerLiter
#> 238                                millimolePerMeterCubed
#> 239                               microequivalentPerLiter
#> 240                               milliequivalentPerLiter
#> 241                                    equivalentPerLiter
#> 242                                              molality
#> 243                                      millimolePerGram
#> 244                                           molePerGram
#> 245                                       molePerKilogram
#> 246                                      micromolePerGram
#> 247                                 candelaPerSquareMeter
#> 248                                candelaPerMeterSquared
#> 249                                metersSquaredPerSecond
#> 250                                   metersSquaredPerDay
#> 251                                     feetSquaredPerDay
#> 252                                     footSquaredPerDay
#> 253                                    meterSquaredPerDay
#> 254                                 meterSquaredPerSecond
#> 255                     kilogramsPerMeterSquaredPerSecond
#> 256                    gramsPerCentimeterSquaredPerSecond
#> 257                           gramsPerMeterSquaredPerYear
#> 258                                 gramsPerHectarePerDay
#> 259                            kilogramsPerHectarePerYear
#> 260                       kilogramsPerMeterSquaredPerYear
#> 261                     gramPerCentimeterSquaredPerSecond
#> 262                                  gramPerDayPerHectare
#> 263                            gramPerMeterSquaredPerYear
#> 264                             kilogramPerHectarePerYear
#> 265                      kilogramPerMeterSquaredPerSecond
#> 266                         kilogramPerMeterSquaredPerDay
#> 267                             gramPerMeterSquaredPerDay
#> 268                        milligramPerMeterSquaredPerDay
#> 269                        kilogramPerMeterSquaredPerYear
#> 270                                      molesPerKilogram
#> 271                                          molesPerGram
#> 272                                     millimolesPerGram
#> 273                             molesPerKilogramPerSecond
#> 274                             nanomolesPerGramPerSecond
#> 275                              molePerKilogramPerSecond
#> 276                              nanomolePerGramPerSecond
#> 277                                nanomolePerGramPerHour
#> 278                                 nanomolePerGramPerDay
#> 279                             micromolePerGramPerSecond
#> 280                               micromolePerGramPerHour
#> 281                                micromolePerGramPerDay
#> 282                                    kilogramsPerSecond
#> 283                                         tonnesPerYear
#> 284                                          gramsPerYear
#> 285                                           gramPerYear
#> 286                                     kilogramPerSecond
#> 287                                          tonnePerYear
#> 288                                 numberPerMeterSquared
#> 289                             numberPerKilometerSquared
#> 290                                      numberPerHectare
#> 291                                   numberPerMeterCubed
#> 292                                        numberPerLiter
#> 293                                   numberPerMilliliter
#> 294                                         metersPerGram
#> 295                                          meterPerGram
#> 296                                         numberPerGram
#> 297                                          gramsPerGram
#> 298                                     microgramsPerGram
#> 299                                           gramPerGram
#> 300                                  milligramPerKilogram
#> 301                                      microgramPerGram
#> 302                                       nanogramPerGram
#> 303                               microgramPerGramPerHour
#> 304                                microgramPerGramPerDay
#> 305                               microgramPerGramPerWeek
#> 306                                nanogramPerGramPerHour
#> 307                   cubicCentimetersPerCubicCentimeters
#> 308                               meterCubedPerMeterCubed
#> 309                                         literPerLiter
#> 310                                    milliliterPerLiter
#> 311                                    microliterPerLiter
#> 312                                     nanoliterPerLiter
#> 313                                           molePerMole
#> 314                                      millimolePerMole
#> 315                                      micromolePerMole
#> 316                                       nanomolePerMole
#> 317                                       molePerKilogram
#> 318                                  millimolePerKilogram
#> 319                                  micromolePerKilogram
#> 320                                   nanomolePerKilogram
#> 321                                               percent
#> 322                                                permil
#> 323                                   wattPerMeterSquared
#> 324                               kilowattPerMeterSquared
#> 325                       wattPerMeterSquaredPerSteradian
#> 326             microwattPerCentimeterSquaredPerSteradian
#> 327                       wattPerMeterSquaredPerNanometer
#> 328             microwattPerCentimeterSquaredPerNanometer
#> 329           wattPerMeterSquaredPerNanometerPerSteradian
#> 330 microwattPerCentimeterSquaredPerNanometerPerSteradian
#> 331                          molePerMeterSquaredPerSecond
#> 332                     micromolePerMeterSquaredPerSecond
#> 333                micromolePerCentimeterSquaredPerSecond
#> 334                        megajoulePerMeterSquaredPerDay
#> 335                                         langleyPerDay
#>                                                      name
#> 1                                           dimensionless
#> 2                                                  second
#> 3                                                   meter
#> 4                                                kilogram
#> 5                                                  kelvin
#> 6                                                 coulomb
#> 7                                                  ampere
#> 8                                                    mole
#> 9                                                 candela
#> 10                                                 number
#> 11                                             cubicMeter
#> 12                                          nominalMinute
#> 13                                            nominalHour
#> 14                                             nominalDay
#> 15                                            nominalWeek
#> 16                                            nominalYear
#> 17                                        nominalLeapYear
#> 18                                               nanogram
#> 19                                              microgram
#> 20                                              milligram
#> 21                                              centigram
#> 22                                               decigram
#> 23                                                   gram
#> 24                                               dekagram
#> 25                                              hectogram
#> 26                                               megagram
#> 27                                                  tonne
#> 28                                                  pound
#> 29                                                    ton
#> 30                                                celsius
#> 31                                             fahrenheit
#> 32                                              nanometer
#> 33                                             micrometer
#> 34                                                 micron
#> 35                                             millimeter
#> 36                                             centimeter
#> 37                                              decimeter
#> 38                                              dekameter
#> 39                                             hectometer
#> 40                                              kilometer
#> 41                                              megameter
#> 42                                               angstrom
#> 43                                                   inch
#> 44                                                Foot_US
#> 45                                                   foot
#> 46                                        Foot_Gold_Coast
#> 47                                                 fathom
#> 48                                           nauticalMile
#> 49                                                   yard
#> 50                                            Yard_Indian
#> 51                                            Link_Clarke
#> 52                                             Yard_Sears
#> 53                                                   mile
#> 54                                             nanosecond
#> 55                                            microsecond
#> 56                                            millisecond
#> 57                                            centisecond
#> 58                                             decisecond
#> 59                                             dekasecond
#> 60                                            hectosecond
#> 61                                             kilosecond
#> 62                                             megasecond
#> 63                                                 minute
#> 64                                                   hour
#> 65                                              kiloliter
#> 66                                             microliter
#> 67                                             milliliter
#> 68                                                  liter
#> 69                                                 gallon
#> 70                                                  quart
#> 71                                                 bushel
#> 72                                              cubicInch
#> 73                                                   pint
#> 74                                             meterCubed
#> 75                                        centimeterCubed
#> 76                                              inchCubed
#> 77                                                 radian
#> 78                                                 degree
#> 79                                                   grad
#> 80                                              steradian
#> 81                                              megahertz
#> 82                                              kilohertz
#> 83                                                  hertz
#> 84                                             millihertz
#> 85                                                 newton
#> 86                                                  joule
#> 87                                                calorie
#> 88                                     britishThermalUnit
#> 89                                              footPound
#> 90                                                langley
#> 91                                                  lumen
#> 92                                                    lux
#> 93                                              becquerel
#> 94                                                   gray
#> 95                                                sievert
#> 96                                                  katal
#> 97                                                  henry
#> 98                                               megawatt
#> 99                                               kilowatt
#> 100                                                  watt
#> 101                                             milliwatt
#> 102                                              megavolt
#> 103                                              kilovolt
#> 104                                                  volt
#> 105                                             millivolt
#> 106                                                 farad
#> 107                                                   ohm
#> 108                                              ohmMeter
#> 109                                       siemensPerMeter
#> 110                                  siemensPerCentimeter
#> 111                                                siemen
#> 112                                               siemens
#> 113                                                 weber
#> 114                                                 tesla
#> 115                                                pascal
#> 116                                            megapascal
#> 117                                            kilopascal
#> 118                                           hectopascal
#> 119                                            atmosphere
#> 120                                                   bar
#> 121                                              millibar
#> 122                                               decibar
#> 123                               kilogramsPerSquareMeter
#> 124                                   gramsPerSquareMeter
#> 125                              milligramsPerSquareMeter
#> 126                                   kilogramsPerHectare
#> 127                                       tonnePerHectare
#> 128                                   poundsPerSquareInch
#> 129                              gramPercentimeterSquared
#> 130                                   gramPerMeterSquared
#> 131                                    kilogramPerHectare
#> 132                               kilogramPerMeterSquared
#> 133                              milligramPerMeterSquared
#> 134                                          poundPerAcre
#> 135                                   poundPerInchSquared
#> 136                                 kilogramPerCubicMeter
#> 137                               milliGramsPerMilliLiter
#> 138                                         gramsPerLiter
#> 139                               milligramsPerCubicMeter
#> 140                                    microgramsPerLiter
#> 141                                    milligramsPerLiter
#> 142                               gramsPerCubicCentimeter
#> 143                                    gramsPerMilliliter
#> 144                                gramPerCentimeterCubed
#> 145                                          gramPerLiter
#> 146                                     gramPerMilliliter
#> 147                                     microgramPerLiter
#> 148                                     milligramPerLiter
#> 149                                milligramPerMeterCubed
#> 150                                 kilogramPerMeterCubed
#> 151                                 megagramPerMeterCubed
#> 152                                milligramPerMilliliter
#> 153                                   gramsPerLiterPerDay
#> 154                          milligramPerMeterCubedPerDay
#> 155                                    gramPerDayPerLiter
#> 156                                       litersPerSecond
#> 157                                  cubicMetersPerSecond
#> 158                                    cubicFeetPerSecond
#> 159                                    footCubedPerSecond
#> 160                                        literPerSecond
#> 161                                   meterCubedPerSecond
#> 162                                           squareMeter
#> 163                                                   are
#> 164                                               hectare
#> 165                                      squareKilometers
#> 166                                     squareMillimeters
#> 167                                     squareCentimeters
#> 168                                                  acre
#> 169                                            squareFoot
#> 170                                            squareYard
#> 171                                            squareMile
#> 172                                     centimeterSquared
#> 173                                           footSquared
#> 174                                      kilometerSquared
#> 175                                          meterSquared
#> 176                                           mileSquared
#> 177                                     millimeterSquared
#> 178                                           yardSquared
#> 179                                  litersPerSquareMeter
#> 180                                        bushelsPerAcre
#> 181                                      litersPerHectare
#> 182                                         bushelPerAcre
#> 183                                       literPerHectare
#> 184                                  literPerMeterSquared
#> 185                                  meterCubedPerHectare
#> 186                             meterCubedPerMeterSquared
#> 187                                meterSquaredPerHectare
#> 188                                squareMeterPerKilogram
#> 189                               meterSquaredPerKilogram
#> 190                                       metersPerSecond
#> 191                                          metersPerDay
#> 192                                            feetPerDay
#> 193                                         feetPerSecond
#> 194                                           feetPerHour
#> 195                                        yardsPerSecond
#> 196                                          milesPerHour
#> 197                                        milesPerSecond
#> 198                                        milesPerMinute
#> 199                                  centimetersPerSecond
#> 200                                  millimetersPerSecond
#> 201                                     centimeterPerYear
#> 202                                                 knots
#> 203                                     kilometersPerHour
#> 204                                   centimeterPerSecond
#> 205                                            footPerDay
#> 206                                           footPerHour
#> 207                                         footPerSecond
#> 208                                           inchPerHour
#> 209                                      kilometerPerHour
#> 210                                                  knot
#> 211                                           meterPerDay
#> 212                                        meterPerSecond
#> 213                                           milePerHour
#> 214                                         milePerMinute
#> 215                                         milePerSecond
#> 216                                      millimeterPerDay
#> 217                                   millimeterPerSecond
#> 218                                         yardPerSecond
#> 219                                metersPerSecondSquared
#> 220                                 meterPerSecondSquared
#> 221                                            waveNumber
#> 222                                          inverseMeter
#> 223                                     inverseCentimeter
#> 224                                 cubicMeterPerKilogram
#> 225                               cubicMicrometersPerGram
#> 226                                 meterCubedPerKilogram
#> 227                                micrometerCubedPerGram
#> 228                                  amperePerSquareMeter
#> 229                                 amperePerMeterSquared
#> 230                                        amperePerMeter
#> 231                                     molePerCubicMeter
#> 232                                              molarity
#> 233                                     molePerMeterCubed
#> 234                                          molePerLiter
#> 235                                     millimolePerLiter
#> 236                                     micromolePerLiter
#> 237                                      nanomolePerLiter
#> 238                                millimolePerMeterCubed
#> 239                               microequivalentPerLiter
#> 240                               milliequivalentPerLiter
#> 241                                    equivalentPerLiter
#> 242                                              molality
#> 243                                      millimolePerGram
#> 244                                           molePerGram
#> 245                                       molePerKilogram
#> 246                                      micromolePerGram
#> 247                                 candelaPerSquareMeter
#> 248                                candelaPerMeterSquared
#> 249                                metersSquaredPerSecond
#> 250                                   metersSquaredPerDay
#> 251                                     feetSquaredPerDay
#> 252                                     footSquaredPerDay
#> 253                                    meterSquaredPerDay
#> 254                                 meterSquaredPerSecond
#> 255                     kilogramsPerMeterSquaredPerSecond
#> 256                    gramsPerCentimeterSquaredPerSecond
#> 257                           gramsPerMeterSquaredPerYear
#> 258                                 gramsPerHectarePerDay
#> 259                            kilogramsPerHectarePerYear
#> 260                       kilogramsPerMeterSquaredPerYear
#> 261                     gramPerCentimeterSquaredPerSecond
#> 262                                  gramPerDayPerHectare
#> 263                            gramPerMeterSquaredPerYear
#> 264                             kilogramPerHectarePerYear
#> 265                      kilogramPerMeterSquaredPerSecond
#> 266                         kilogramPerMeterSquaredPerDay
#> 267                             gramPerMeterSquaredPerDay
#> 268                        milligramPerMeterSquaredPerDay
#> 269                        kilogramPerMeterSquaredPerYear
#> 270                                      molesPerKilogram
#> 271                                          molesPerGram
#> 272                                     millimolesPerGram
#> 273                             molesPerKilogramPerSecond
#> 274                             nanomolesPerGramPerSecond
#> 275                              molePerKilogramPerSecond
#> 276                              nanomolePerGramPerSecond
#> 277                                nanomolePerGramPerHour
#> 278                                 nanomolePerGramPerDay
#> 279                             micromolePerGramPerSecond
#> 280                               micromolePerGramPerHour
#> 281                                micromolePerGramPerDay
#> 282                                    kilogramsPerSecond
#> 283                                         tonnesPerYear
#> 284                                          gramsPerYear
#> 285                                           gramPerYear
#> 286                                     kilogramPerSecond
#> 287                                          tonnePerYear
#> 288                                 numberPerMeterSquared
#> 289                             numberPerKilometerSquared
#> 290                                      numberPerHectare
#> 291                                   numberPerMeterCubed
#> 292                                        numberPerLiter
#> 293                                   numberPerMilliliter
#> 294                                         metersPerGram
#> 295                                          meterPerGram
#> 296                                         numberPerGram
#> 297                                          gramsPerGram
#> 298                                     microgramsPerGram
#> 299                                           gramPerGram
#> 300                                  milligramPerKilogram
#> 301                                      microgramPerGram
#> 302                                       nanogramPerGram
#> 303                               microgramPerGramPerHour
#> 304                                microgramPerGramPerDay
#> 305                               microgramPerGramPerWeek
#> 306                                nanogramPerGramPerHour
#> 307                   cubicCentimetersPerCubicCentimeters
#> 308                               meterCubedPerMeterCubed
#> 309                                         literPerLiter
#> 310                                    milliliterPerLiter
#> 311                                    microliterPerLiter
#> 312                                     nanoliterPerLiter
#> 313                                           molePerMole
#> 314                                      millimolePerMole
#> 315                                      micromolePerMole
#> 316                                       nanomolePerMole
#> 317                                       molePerKilogram
#> 318                                  millimolePerKilogram
#> 319                                  micromolePerKilogram
#> 320                                   nanomolePerKilogram
#> 321                                               percent
#> 322                                                permil
#> 323                                   wattPerMeterSquared
#> 324                               kilowattPerMeterSquared
#> 325                       wattPerMeterSquaredPerSteradian
#> 326             microwattPerCentimeterSquaredPerSteradian
#> 327                       wattPerMeterSquaredPerNanometer
#> 328             microwattPerCentimeterSquaredPerNanometer
#> 329           wattPerMeterSquaredPerNanometerPerSteradian
#> 330 microwattPerCentimeterSquaredPerNanometerPerSteradian
#> 331                          molePerMeterSquaredPerSecond
#> 332                     micromolePerMeterSquaredPerSecond
#> 333                micromolePerCentimeterSquaredPerSecond
#> 334                        megajoulePerMeterSquaredPerDay
#> 335                                         langleyPerDay
#>                           unitType                         udunitsSynonym
#> 1                    dimensionless                                       
#> 2                             time                                 second
#> 3                           length                                  meter
#> 4                             mass                               kilogram
#> 5                      temperature                                 kelvin
#> 6                           charge                                coulomb
#> 7                          current                                 ampere
#> 8                           amount                                   mole
#> 9                       luminosity                                candela
#> 10                   dimensionless                                  count
#> 11                          volume                                meter^3
#> 12                            time                                 minute
#> 13                            time                                   hour
#> 14                            time                                    day
#> 15                            time                                   week
#> 16                            time                            common_year
#> 17                            time                              leap_year
#> 18                            mass                               nanogram
#> 19                            mass                              microgram
#> 20                            mass                              milligram
#> 21                            mass                              centigram
#> 22                            mass                               decigram
#> 23                            mass                                   gram
#> 24                            mass                               dekagram
#> 25                            mass                              hectogram
#> 26                            mass                               megagram
#> 27                            mass                             metric_ton
#> 28                            <NA>                      avoirdupois_pound
#> 29                            <NA>                              short_ton
#> 30                            <NA>                                celsius
#> 31                            <NA>                             fahrenheit
#> 32                            <NA>                              nanometer
#> 33                            <NA>                             micrometer
#> 34                            <NA>                             micrometer
#> 35                            <NA>                             millimeter
#> 36                            <NA>                             centimeter
#> 37                            <NA>                              decimeter
#> 38                            <NA>                              dekameter
#> 39                            <NA>                             hectometer
#> 40                            <NA>                              kilometer
#> 41                            <NA>                              megameter
#> 42                            <NA>                               angstrom
#> 43                            <NA>                     international_inch
#> 44                            <NA>                         US_survey_foot
#> 45                            <NA>                     international_foot
#> 46                            <NA>                                       
#> 47                            <NA>                                 fathom
#> 48                            <NA>                          nautical_mile
#> 49                            <NA>                     international_yard
#> 50                            <NA>                                       
#> 51                            <NA>                                       
#> 52                            <NA>                                       
#> 53                            <NA>                     international_mile
#> 54                            <NA>                             nanosecond
#> 55                            <NA>                            microsecond
#> 56                            <NA>                            millisecond
#> 57                            <NA>                            centisecond
#> 58                            <NA>                             decisecond
#> 59                            <NA>                             dekasecond
#> 60                            <NA>                            hectosecond
#> 61                            <NA>                             kilosecond
#> 62                            <NA>                             megasecond
#> 63                            <NA>                                 minute
#> 64                            <NA>                                   hour
#> 65                          volume                              kiloliter
#> 66                          volume                             microliter
#> 67                          volume                             milliliter
#> 68                          volume                                  liter
#> 69                            <NA>                       US_liquid_gallon
#> 70                            <NA>                        US_liquid_quart
#> 71                          volume                                 bushel
#> 72                          volume                   international_inch^3
#> 73                            <NA>                         US_liquid_pint
#> 74                          volume                                meter^3
#> 75                          volume                           centimeter^3
#> 76                          volume                   international_inch^3
#> 77                           angle                                 radian
#> 78                           angle                             arc_degree
#> 79                           angle                                       
#> 80                           angle                              steradian
#> 81                       frequency                              megahertz
#> 82                       frequency                              kilohertz
#> 83                       frequency                                  hertz
#> 84                       frequency                             millihertz
#> 85                           force                                 newton
#> 86                          energy                                  joule
#> 87                          energy                             IT_calorie
#> 88                          energy                                 IT_Btu
#> 89                          energy         international_foot pound_force
#> 90              arealEnergyDensity                                langley
#> 91                      luminosity                                  lumen
#> 92                     illuminance                                    lux
#> 93         radionucleotideActivity                              becquerel
#> 94                  specificEnergy                                   gray
#> 95                  doseEquivalent                                sievert
#> 96               catalyticActivity                                  katal
#> 97                      inductance                                  henry
#> 98                           power                               megawatt
#> 99                           power                               kilowatt
#> 100                          power                                   watt
#> 101                          power                              milliwatt
#> 102            potentialDifference                               megavolt
#> 103            potentialDifference                               kilovolt
#> 104            potentialDifference                                   volt
#> 105            potentialDifference                              millivolt
#> 106                    capacitance                                  farad
#> 107                     resistance                                    ohm
#> 108                    resistivity                              ohm meter
#> 109                                                         siemens/meter
#> 110                                                    siemens/centimeter
#> 111                    conductance                                siemens
#> 112                                                               siemens
#> 113                   magneticFlux                                  weber
#> 114            magneticFluxDensity                                  tesla
#> 115                       pressure                                 pascal
#> 116                       pressure                             megapascal
#> 117                       pressure                             kilopascal
#> 118                       pressure                            hectopascal
#> 119                       pressure                    standard_atmosphere
#> 120                       pressure                                    bar
#> 121                       pressure                               millibar
#> 122                       pressure                                decibar
#> 123               arealMassDensity                       kilogram/meter^2
#> 124               arealMassDensity                           gram/meter^2
#> 125               arealMassDensity                      milligram/meter^2
#> 126               arealMassDensity                       kilogram/hectare
#> 127               arealMassDensity                     metric_ton/hectare
#> 128               arealMassDensity avoirdupois_pound/international_inch^2
#> 129               arealMassDensity                              gram/cm^2
#> 130               arealMassDensity                           gram/meter^2
#> 131               arealMassDensity                       kilogram/hectare
#> 132               arealMassDensity                       kilogram/meter^2
#> 133               arealMassDensity                      milligram/meter^2
#> 134               arealMassDensity                 avoirdupois_pound/acre
#> 135               arealMassDensity avoirdupois_pound/international_inch^2
#> 136                    massDensity                       kilogram/meter^3
#> 137                    massDensity                   milligram/milliliter
#> 138                    massDensity                             gram/liter
#> 139                    massDensity                      milligram/meter^3
#> 140                    massDensity                        microgram/liter
#> 141                    massDensity                        milligram/liter
#> 142                    massDensity                      gram/centimeter^3
#> 143                    massDensity                        gram/milliliter
#> 144                    massDensity                      gram/centimeter^3
#> 145                    massDensity                             gram/liter
#> 146                    massDensity                        gram/milliliter
#> 147                    massDensity                        microgram/liter
#> 148                    massDensity                        milligram/liter
#> 149                    massDensity                      milligram/meter^3
#> 150                    massDensity                       kilogram/meter^3
#> 151                    massDensity                       megagram/meter^3
#> 152                    massDensity                   milligram/milliliter
#> 153      volumetricMassDensityRate                         gram/liter/day
#> 154      volumetricMassDensityRate                  milligram/meter^3/day
#> 155      volumetricMassDensityRate                         gram/day/liter
#> 156                 volumetricRate                           liter/second
#> 157                 volumetricRate                         meter^3/second
#> 158                 volumetricRate            international_foot^3/second
#> 159                 volumetricRate            international_foot^3/second
#> 160                 volumetricRate                           liter/second
#> 161                 volumetricRate                         meter^3/second
#> 162                           area                                meter^2
#> 163                           area                                    are
#> 164                           area                                hectare
#> 165                           area                            kilometer^2
#> 166                           area                           millimeter^2
#> 167                           area                           centimeter^2
#> 168                           area                                   acre
#> 169                           area                   international_foot^2
#> 170                           area                   international_yard^2
#> 171                           area                   international_mile^2
#> 172                           area                           centimeter^2
#> 173                           area                   international_foot^2
#> 174                           area                            kilometer^2
#> 175                           area                                meter^2
#> 176                           area                   international_mile^2
#> 177                           area                           millimeter^2
#> 178                           area                   international_yard^2
#> 179                 volumetricArea                          liter/meter^2
#> 180                 volumetricArea                            bushel/acre
#> 181                 volumetricArea                          liter/hectare
#> 182                 volumetricArea                            bushel/acre
#> 183                 volumetricArea                          liter/hectare
#> 184                 volumetricArea                          liter/meter^2
#> 185                 volumetricArea                            m^3/hectare
#> 186                 volumetricArea                                m^3/m^2
#> 187                 volumetricArea                            m^2/hectare
#> 188                   specificArea                       meter^2/kilogram
#> 189                   specificArea                       meter^2/kilogram
#> 190                          speed                           meter/second
#> 191                          speed                              meter/day
#> 192                          speed                 international_foot/day
#> 193                          speed              international_foot/second
#> 194                          speed                international_foot/hour
#> 195                          speed              international_yard/second
#> 196                          speed                international_mile/hour
#> 197                          speed              international_mile/second
#> 198                          speed              international_mile/minute
#> 199                          speed                      centimeter/second
#> 200                          speed                      millimeter/second
#> 201                          speed                 centimeter/common_year
#> 202                          speed                     international_knot
#> 203                          speed                         kilometer/hour
#> 204                          speed                      centimeter/second
#> 205                          speed                 international_foot/day
#> 206                          speed                international_foot/hour
#> 207                          speed              international_foot/second
#> 208                          speed                international_inch/hour
#> 209                          speed                         kilometer/hour
#> 210                          speed                     international_knot
#> 211                          speed                              meter/day
#> 212                          speed                           meter/second
#> 213                          speed                international_mile/hour
#> 214                          speed              international_mile/minute
#> 215                          speed              international_mile/second
#> 216                          speed                         millimeter/day
#> 217                          speed                      millimeter/second
#> 218                          speed              international_yard/second
#> 219                   acceleration                         meter/second^2
#> 220                   acceleration                         meter/second^2
#> 221               lengthReciprocal                               meter^-1
#> 222               lengthReciprocal                               meter^-1
#> 223               lengthReciprocal                               meter^-1
#> 224                 specificVolume                       meter^3/kilogram
#> 225                 specificVolume                      micrometer^3/gram
#> 226                 specificVolume                       meter^3/kilogram
#> 227                 specificVolume                      micrometer^3/gram
#> 228                 currentDensity                         ampere/meter^2
#> 229                 currentDensity                         ampere/meter^2
#> 230          magneticFieldStrength                           ampere/meter
#> 231 amountOfSubstanceConcentration                           mole/meter^3
#> 232 amountOfSubstanceConcentration                             mole/liter
#> 233 amountOfSubstanceConcentration                           mole/meter^3
#> 234 amountOfSubstanceConcentration                             mole/liter
#> 235 amountOfSubstanceConcentration                        millimole/liter
#> 236 amountOfSubstanceConcentration                        micromole/liter
#> 237 amountOfSubstanceConcentration                         nanomole/liter
#> 238 amountOfSubstanceConcentration                      millimole/meter^3
#> 239 amountOfSubstanceConcentration                                   <NA>
#> 240 amountOfSubstanceConcentration                                   <NA>
#> 241 amountOfSubstanceConcentration                                   <NA>
#> 242        amountOfSubstanceWeight                          mole/kilogram
#> 243        amountOfSubstanceWeight                         millimole/gram
#> 244        amountOfSubstanceWeight                              mole/gram
#> 245        amountOfSubstanceWeight                          mole/kilogram
#> 246        amountOfSubstanceWeight                         micromole/gram
#> 247                      luminance                        candela/meter^2
#> 248                      luminance                        candela/meter^2
#> 249                 transmissivity                         meter^2/second
#> 250                 transmissivity                            meter^2/day
#> 251                 transmissivity               international_foot^2/day
#> 252                 transmissivity               international_foot^2/day
#> 253                 transmissivity                            meter^2/day
#> 254                 transmissivity                         meter^2/second
#> 255                       massFlux                kilogram/meter^2/second
#> 256                       massFlux               gram/centimeter^2/second
#> 257                       massFlux               gram/meter^2/common_year
#> 258                       massFlux                       gram/hectare/day
#> 259                       massFlux           kilogram/hectare/common_year
#> 260                       massFlux           kilogram/meter^2/common_year
#> 261                       massFlux               gram/centimeter^2/second
#> 262                       massFlux                       gram/day/hectare
#> 263                       massFlux               gram/meter^2/common_year
#> 264                       massFlux           kilogram/hectare/common_year
#> 265                       massFlux                kilogram/meter^2/second
#> 266                       massFlux                   kilogram/meter^2/day
#> 267                       massFlux                   kilogram/meter^2/day
#> 268                       massFlux                  milligram/meter^2/day
#> 269                       massFlux           kilogram/meter^2/common_year
#> 270        amountOfSubstanceWeight                          mole/kilogram
#> 271        amountOfSubstanceWeight                              mole/gram
#> 272        amountOfSubstanceWeight                         millimole/gram
#> 273    amountOfSubstanceWeightRate                   mole/kilogram/second
#> 274    amountOfSubstanceWeightRate                   nanomole/gram/second
#> 275    amountOfSubstanceWeightRate                   mole/kilogram/second
#> 276    amountOfSubstanceWeightRate                   nanomole/gram/second
#> 277    amountOfSubstanceWeightRate                     nanomole/gram/hour
#> 278    amountOfSubstanceWeightRate                      nanomole/gram/day
#> 279    amountOfSubstanceWeightRate                  micromole/gram/second
#> 280    amountOfSubstanceWeightRate                    micromole/gram/hour
#> 281    amountOfSubstanceWeightRate                     micromole/gram/day
#> 282                       massRate                        kilogram/second
#> 283                       massRate                 metric_ton/common_year
#> 284                       massRate                       gram/common_year
#> 285                       massRate                       gram/common_year
#> 286                       massRate                        kilogram/second
#> 287                       massRate                 metric_ton/common_year
#> 288                   arealDensity                          count/meter^2
#> 289                   arealDensity                      count/kilometer^2
#> 290                   arealDensity                          count/hectare
#> 291              volumetricDensity                          count/meter^3
#> 292              volumetricDensity                            count/liter
#> 293              volumetricDensity                       count/milliliter
#> 294             massSpecificLength                             meter/gram
#> 295             massSpecificLength                             meter/gram
#> 296              massSpecificCount                             count/gram
#> 297                    massPerMass                              gram/gram
#> 298                    massPerMass                         microgram/gram
#> 299                    massPerMass                              gram/gram
#> 300                    massPerMass                     milligram/kilogram
#> 301                    massPerMass                         microgram/gram
#> 302                    massPerMass                          nanogram/gram
#> 303                massPerMassRate                    microgram/gram/hour
#> 304                massPerMassRate                     microgram/gram/day
#> 305                massPerMassRate                    microgram/gram/week
#> 306                massPerMassRate                     nanogram/gram/hour
#> 307                volumePerVolume              centimeter^3/centimeter^3
#> 308                volumePerVolume                        meter^3/meter^3
#> 309                volumePerVolume                            liter/liter
#> 310                volumePerVolume                       milliliter/liter
#> 311                volumePerVolume                       microliter/liter
#> 312                volumePerVolume                        nanoliter/liter
#> 313                                                             mole/mole
#> 314                                                        millimole/mole
#> 315                                                        micromole/mole
#> 316                                                         nanomole/mole
#> 317                                                         mole/kilogram
#> 318                                                    millimole/kilogram
#> 319                                                    micromole/kilogram
#> 320                                                     nanomole/kilogram
#> 321                  dimensionless                                percent
#> 322                  dimensionless                                percent
#> 323                                                          watt/meter^2
#> 324                                                      kilowatt/meter^2
#> 325                                                watt/meter^2/steradian
#> 326                                      microwatt/centimeter^2/steradian
#> 327                                                       watt/meter^2/nm
#> 328                                             microwatt/centimeter^2/nm
#> 329                                             watt/meter^2/nm/steradian
#> 330                                   microwatt/centimeter^2/nm/steradian
#> 331                                                   mole/meter^2/second
#> 332                                              micromole/meter^2/second
#> 333                                         micromole/centimeter^2/second
#> 334         arealEnergyDensityRate                      megajoule/m^2/day
#> 335         arealEnergyDensityRate                            langley/day
#>                                                                                                                                                                                                                                                                      description
#> 1                                                                                                                                                                                                                      a designation asserting the absence of an associated unit
#> 2                                                                                                                                                                                                                                                                SI unit of time
#> 3                                                                                                                                                                                                                                                              SI unit of length
#> 4                                                                                                                                                                                                                                                                SI unit of mass
#> 5                                                                                                                                                                                                                                                         SI unit of temperature
#> 6                                                                                                                                                                                                                                                              SI unit of charge
#> 7                                                                                                                                                                                                                                                  SI unit of electrical current
#> 8                                                                                                                                                                                                                                                    SI unit of substance amount
#> 9                                                                                                                                        SI base unit of luminous intensity (luminous power per unti solid angle emitted\n    by a point light source in a particular direction)
#> 10                                                                                                                                                                                                                                                          a quantity or amount
#> 11                                                                                                                                                                                                                                                                   cubic meter
#> 12                                                                                                                                                                                                                         one minute of time excluding leap seconds, 60 seconds
#> 13                                                                                                                                                                                                                                 one hour excluding leap seconds, 3600 seconds
#> 14                                                                                                                                                                                                                                 one day excluding leap seconds, 86400 seconds
#> 15                                                                                                                                                                                                                                one day excluding leap seconds, 604800 seconds
#> 16                                                                                                                                                                                                               one year excluding leap seconds and leap days, 31536000 seconds
#> 17                                                                                                                                                                                                                     one 366 day year excluding leap seconds, 31622400 seconds
#> 18                                                                                                                                                                                                                                                             0.000000000001 kg
#> 19                                                                                                                                                                                                                                                                0.000000001 kg
#> 20                                                                                                                                                                                                                                                                   0.000001 kg
#> 21                                                                                                                                                                                                                                                                    0.00001 kg
#> 22                                                                                                                                                                                                                                                                     0.0001 kg
#> 23                                                                                                                                                                                                                                                                      0.001 kg
#> 24                                                                                                                                                                                                                                                                        .01 kg
#> 25                                                                                                                                                                                                                                                                         .1 kg
#> 26                                                                                                                                                                                                                                                                       1000 kg
#> 27                                                    unit of mass equal to 1,000 kilograms, equivalent to approximately 2,204.6 \n      pounds,1.102 short tons (US) or 0.984 long tons (imperial). \n      Not part of the SI, but accepted for use with SI units and prefixes
#> 28                                                                                                               1 pound (symbol lb) in the Avoirdupois (commerce) scale, and defined \n      as exactly 0.45359237 kg. Also equal to 16 avoirdupois ounces and to 7,000 grains.
#> 29                                                                                                                                                                                                                                            standard US (short) ton = 2000 lbs
#> 30                                                                                                                                                                                                                                                  A common unit of temperature
#> 31                                                                                                                                                            unit for temperature on the scale in which water freezes at 32 and boils \n      at 212 under standard conditions.
#> 32                                                                                                                                                                                                                                                             .000000001 meters
#> 33                                                                                                                                                                                                                                                                .000001 meters
#> 34                                                                                                                                                                                                                                                                .000001 meters
#> 35                                                                                                                                                                                                                                                                   .001 meters
#> 36                                                                                                                                                                                                                                                                    .01 meters
#> 37                                                                                                                                                                                                                                                                     .1 meters
#> 38                                                                                                                                                                                                                                                                     10 meters
#> 39                                                                                                                                                                                                                                                                    100 meters
#> 40                                                                                                                                                                                                                                                                   1000 meters
#> 41                                                                                                                                                                                                                                                                1000000 meters
#> 42                                                                                                                                                                                                                                                           1/10000000000 meter
#> 43                                                                                                                                                               unit of length in the (British) imperial and United States systems \n      usually understood as 1/12 f a foot.
#> 44                                                                                                                                                                                                                                                                     12 inches
#> 45                                                                                                                                                                                                                                                                     12 inches
#> 46                                                                                                                                                                                                                                                                     12 inches
#> 47                                                                                                                                                                                                                                                                        6 feet
#> 48                                                                                                                                                             defined as exactly 1,852 meters (6,076.1 ft; 1.1508 mi). Historically, \n      defined as one minute of latitude.
#> 49                                                                                                                                                                                                                                                                        3 feet
#> 50                                                                                                                                                                                       This is an ESRI unit and the multiplier comes from ESRI. It may not be\n      accurate.
#> 51                                                                                                                                                                                       This is an ESRI unit and the multiplier comes from ESRI. It may not be\n      accurate.
#> 52                                                                                                                                                                                       This is an ESRI unit and the multiplier comes from ESRI. It may not be\n      accurate.
#> 53                                                                                                                                                                                                                                                    5280 ft or 1609.344 meters
#> 54                                                                                                                                                                                                                                                         1/1000000 of a second
#> 55                                                                                                                                                                                                                                                          1/100000 of a second
#> 56                                                                                                                                                                                                                                                            1/1000 of a second
#> 57                                                                                                                                                                                                                                                             1/100 of a second
#> 58                                                                                                                                                                                                                                                              1/10 of a second
#> 59                                                                                                                                                                                                                                                                    10 seconds
#> 60                                                                                                                                                                                                                                                                   100 seconds
#> 61                                                                                                                                                                                                                                                                  1000 seconds
#> 62                                                                                                                                                                                                                                                               1000000 seconds
#> 63                                                                                                                                                                                                                                                                    60 seconds
#> 64                                                                                                                                                                                                                                                                  3600 seconds
#> 65                                                                                                                                                                                                                                                                 1 cubic meter
#> 66                                                                                                                                                                                                                                                          1/1000000 of a liter
#> 67                                                                                                                                                                                                                                                             1/1000 of a liter
#> 68                                                                                                                                                                                                                                                                     1000 cm^3
#> 69                                                                                                                                                                                                                                                              US liquid gallon
#> 70                                                                                                                                                                                                                                                               US liquid quart
#> 71                                                                                                                                                                                                                                                    1 bushel = 35.23907 liters
#> 72                                                                                                                                                                                                                                                                    cubic inch
#> 73                                                                                                                                                                                                                                                                US liquid pint
#> 74                                                                                                                                                                                                                                                                   cubic meter
#> 75                                                                                                                                                                                                                                                                   cubic meter
#> 76                                                                                                                                                                                                                                        micromoles per square meter per second
#> 77                                                                                                                                                                                                                                          2 pi radians comprise a unit circle.
#> 78                                                                                                                                                                                                                                            360 degrees comprise a unit circle
#> 79                                                                                                                                                                                                                            a plane angle equivalent to 1/400 of a full circle
#> 80                                                                          standard unit of solid angle measure, it is the solid angle which cuts out an area\n      on a sphere that is the square of the sphere's radius; as a ratio of two areas, it has no\n      dimension
#> 81                                                                                                                                                                                                                                                                     megahertz
#> 82                                                                                                                                                                                                                                                                     kilohertz
#> 83                                                                                                                                                                                                          derived unit of frequency in the SI, defined as one cycle per second
#> 84                                                                                                                                                                                                                                                                    millihertz
#> 85                                                                                                                                                                                                                                                                        newton
#> 86                                                                                                                                                                                                                                                                   joule = N*m
#> 87                                                                                                                  unit of energy: amount of energy to raise the temperature of one gram of water \n      by one degree Celsius at a pressure of one atmosphere. cal = 4.1868 J
#> 88                                                                                                                                                                                                                                           an energy unit: 1 btu = 1055.0559 J
#> 89                                                                                                                                                                                                                                                         1 ft-lbs = 1.355818 J
#> 90                                                                                                                                                                                                                    unit of energy density = 41840 joule/m^2, = 1 calorie/cm^2
#> 91                                                                                                                                      SI unit for the total quantity of visible light in a defined beam or angle.\n      1 lumen/m^2 = 1 lux. 1 lumen = 1 candela * steradian 
#> 92                                                                                                                                                                              SI derived unit for illuminance, or luminous flux per unit area. 1 lx = 1 lm/m^2 = 1 cd * sr/m^2
#> 93                                                                                               SI derived unit of radioactivity. the activity of a quantity of radioactive material in which \n      one nucleus decays per second, and equivalent to an inverse second, s^-1.
#> 94                                                                                                                                   SI derived unit of ionizing radiation, defined as the absorption of one joule of \n      radiation energy per kilogram of matter (= 1 J/kg)
#> 95                                                                                                              SI derived unit of ionizing radiation dose (health effect of low levels of ionizing \n      radiation on humans). 1 Sv =  100 rem (rem is an older, non-SI unit)
#> 96                                                                                                                                      derived SI unit for quantifying enzymatic activity.A property of the catalyst \n      (not rate of reaction), expressed in moles/second.
#> 97                                                                                                                                                                                                      SI derived unit for inductance; in SI base units: kg * m^2 * s^-2 * A^-2
#> 98                                                                                                                                                                                                                 unit of power, to quantify rate of energy transfer. 1 W = J/s
#> 99                                                                                                                                                                                                                 unit of power, to quantify rate of energy transfer. 1 W = J/s
#> 100                                                                                                                                                                                                                unit of power, to quantify rate of energy transfer. 1 W = J/s
#> 101                                                                                                                                                                                                                unit of power, to quantify rate of energy transfer. 1 W = J/s
#> 102                                                                                                                                            Derived unit for electric potential, electric potential difference, \n      and electromotive force. 1 V = kg * m^2 * s^-3 * A^-1
#> 103                                                                                                                                            Derived unit for electric potential, electric potential difference, \n      and electromotive force. 1 V = kg * m^2 * s^-3 * A^-1
#> 104                                                                                                                                            Derived unit for electric potential, electric potential difference, \n      and electromotive force. 1 V = kg * m^2 * s^-3 * A^-1
#> 105                                                                                                                                            Derived unit for electric potential, electric potential difference, \n      and electromotive force. 1 V = kg * m^2 * s^-3 * A^-1
#> 106                                                                                                                                        SI derived unit of electrical capacitance, the ability of a body to store an \n      electrical charge. 1 F = s^4 * A^2 *m^-2 * kg^-1
#> 107                                                                      an electrical resistance between two points of a conductor when a constant potential \n      difference of one volt, \n      applied to these points, produces in the conductor a current of one ampere
#> 108                                                                                       SI unit of electrical resistivity (fundamental property that quantifies how strongly a material \n      opposes the flow of electric current). reciprocal of electrical conductivity. 
#> 109                                                                                                                                                                            SI unit for conductivity, measure of a material's ability to conduct an \n      electric current.
#> 110                                                                                                                                                                            SI unit for conductivity, measure of a material's ability to conduct an \n      electric current.
#> 111                                                                                                                                                                                                                                                                      siemens
#> 112                                            SI derived unit of electric conductance, susceptance and admittance \n      (reciprocals of resistance, reactance, and impedance respectively). One siemens is equal \n      to the reciprocal of one ohm (and also called "mho")
#> 113                                                                                                                                                                                                                                                 the SI unit of magnetic flux
#> 114                                                                                                                                                                                                      unit for flux density. 1 tesla = 1 Wb/m^2 (one weber per square meter).
#> 115                                                                                                                                                                                                                         SI derived unit of pressure, 1 pascal = 1 newton/m^2
#> 116                                                                                                                                                                                                                         SI derived unit of pressure, 1 pascal = 1 newton/m^2
#> 117                                                                                                                                                                                                                         SI derived unit of pressure, 1 pascal = 1 newton/m^2
#> 118                                                                                                                                                                                                                         SI derived unit of pressure, 1 pascal = 1 newton/m^2
#> 119                                                                                                                                                              unit of pressure defined as 101325 Pa (1.01325 bar), sometimes used as a \n      reference or standard pressure
#> 120                                                                                                                                                                                                      non-SI unit for pressure (deprecated in some fields). 1 bar = 100000 Pa
#> 121                                                                                                                                                                                            non-SI unit for pressure (deprecated in some fields). 1 millibar = 1 hPa (100 Pa)
#> 122                                                                                                             non-SI unit for pressure. 1 decibar = .1 bar. Decibars are commonly used in aquatic \n      environments because 1 db is approximately equal to depth in meters.
#> 123                                                                                                                                                                                                                                                   kilograms per square meter
#> 124                                                                                                                                                                                                                                                       grams per square meter
#> 125                                                                                                                                                                                                                                                  milligrams Per Square Meter
#> 126                                                                                                                                                                                                                                                        kilograms per hectare
#> 127                                                                                                                                                                                                                                              metric ton or tonne per hectare
#> 128                                                                                                                                                                                                                                                              lbs/square inch
#> 129                                                                                                                                                                                                                                                       grams per square meter
#> 130                                                                                                                                                                                                                                                       grams per square meter
#> 131                                                                                                                                                                                                                                                        kilograms per hectare
#> 132                                                                                                                                                                                                                                                   kilograms per square meter
#> 133                                                                                                                                                                                                                                                  milligrams Per Square Meter
#> 134                                                                                                                                                                                                                                                  avoirdupois pounds per acre
#> 135                                                                                                                                                                                                                                           avoirdupois pounds per square inch
#> 136                                                                                                                                                                                                                                                     kilogram per cubic meter
#> 137                                                                                                                                                                                                                                                    milligrams per milliliter
#> 138                                                                                                                                                                                                                                                              grams per liter
#> 139                                                                                                                                                                                                                                                   milligrams Per Cubic Meter
#> 140                                                                                                                                                                                                                                                             micrograms/liter
#> 141                                                                                                                                                                                                                                                             milligrams/liter
#> 142                                                                                                                                                                                                                                                   grams per cubic centimeter
#> 143                                                                                                                                                                                                                                                         grams per milliliter
#> 144                                                                                                                                                                                                                                                   grams per cubic centimeter
#> 145                                                                                                                                                                                                                                                              grams per liter
#> 146                                                                                                                                                                                                                                                         grams per milliliter
#> 147                                                                                                                                                                                                                                                             micrograms/liter
#> 148                                                                                                                                                                                                                                                             milligrams/liter
#> 149                                                                                                                                                                                                                                                   milligrams Per Cubic Meter
#> 150                                                                                                                                                                                                                                                    kilograms per cubic meter
#> 151                                                                                                                                                                                                                                                    megagrams per cubic meter
#> 152                                                                                                                                                                                                                                       micromoles per square meter per second
#> 153                                                                                                                                                                                                                                                    grams Per (Liter Per Day)
#> 154                                                                                                                                                                                                                                            milligram per cubic meter per day
#> 155                                                                                                                                                                                                                                                    grams Per (Liter Per Day)
#> 156                                                                                                                                                                                                                                                            liters per second
#> 157                                                                                                                                                                                                                                                      cubic meters per second
#> 158                                                                                                                                                                                                                                                        cubic feet per second
#> 159                                                                                                                                                                                                                                                        cubic feet per second
#> 160                                                                                                                                                                                                                                                            liters per second
#> 161                                                                                                                                                                                                                                                      cubic meters per second
#> 162                                                                                                                                                                                                                                                                square meters
#> 163                                                                                                                                                                                                                                                            100 square meters
#> 164                                                                                                                                                                                                                                              1 hectare is 10^4 square meters
#> 165                                                                                                                                                                                                                                                            square kilometers
#> 166                                                                                                                                                                                                                                                            square millmeters
#> 167                                                                                                                                                                                                                                                           square centimeters
#> 168                                                                                                                                                                                                                 1 acre = 4046.8564 square meters or 1 hectare = 2.4710 acres
#> 169                                                                                                                                                                                                                                                            12 inches squared
#> 170                                                                                                                                                                                                                                                            36 inches squared
#> 171                                                                                                                                                                                                                                                               1 mile squared
#> 172                                                                                                                                                                                                                                                            square centimeter
#> 173                                                                                                                                                                                                                                                            12 inches squared
#> 174                                                                                                                                                                                                                                                             square kilometer
#> 175                                                                                                                                                                                                                                                                square meters
#> 176                                                                                                                                                                                                                                                               1 mile squared
#> 177                                                                                                                                                                                                                                                            square millimeter
#> 178                                                                                                                                                                                                                                                            36 inches squared
#> 179                                                                                                                                                                                                                                                      liters per square meter
#> 180                                                                                                                                                                                          bushels per acre, 1 bushel = 35.23907 liters/1 acre = 4046.8564\n      squareMeters
#> 181                                                                                                                                                                                                                                                           liters per hectare
#> 182                                                                                                                                                                                          bushels per acre, 1 bushel = 35.23907 liters/1 acre = 4046.8564\n      squareMeters
#> 183                                                                                                                                                                                                                                                           liters per hectare
#> 184                                                                                                                                                                                                                                                      liters per square meter
#> 185                                                                                                                                                                                                                                                      meter cubed per hectare
#> 186                                                                                                                                                                                                                                                meter cubed per meter squared
#> 187                                                                                                                                                                                                                                                    meter squared per hectare
#> 188                                                                                                                                                                                                                                                   square meters per kilogram
#> 189                                                                                                                                                                                                                                                   square meters per kilogram
#> 190                                                                                                                                                                                                                                                            meters per second
#> 191                                                                                                                                                                                                                                                               meters per day
#> 192                                                                                                                                                                                                                                                                 feet per day
#> 193                                                                                                                                                                                                                                                              feet per second
#> 194                                                                                                                                                                                                                                                                feet per hour
#> 195                                                                                                                                                                                                                                                             yards per second
#> 196                                                                                                                                                                                                                                                               miles per hour
#> 197                                                                                                                                                                                                                                                             miles per second
#> 198                                                                                                                                                                                                                                                             miles per minute
#> 199                                                                                                                                                                                                                                                       centimeters per second
#> 200                                                                                                                                                                                                                                                       millimeters per second
#> 201                                                                                                                                                                                                                                                          centimeter Per Year
#> 202                                                                                                                                                                                                                                                                        knots
#> 203                                                                                                                                                                                                                                                                        km/hr
#> 204                                                                                                                                                                                                                                                       centimeters per second
#> 205                                                                                                                                                                                                                                                                 feet per day
#> 206                                                                                                                                                                                                                                                                feet per hour
#> 207                                                                                                                                                                                                                                                              feet per second
#> 208                                                                                                                                                                                                                                                              inches per hour
#> 209                                                                                                                                                                                                                                                                        km/hr
#> 210                                                                                                                                                                                                     unit of speed equal to one nautical mile per hour, exactly 1.852 km/hour
#> 211                                                                                                                                                                                                                                                               meters per day
#> 212                                                                                                                                                                                                                                                            meters per second
#> 213                                                                                                                                                                                                                                                               miles per hour
#> 214                                                                                                                                                                                                                                                             miles per minute
#> 215                                                                                                                                                                                                                                                             miles per second
#> 216                                                                                                                                                                                                                                                          millimeters per day
#> 217                                                                                                                                                                                                                                                       millimeters per second
#> 218                                                                                                                                                                                                                                                             yards per second
#> 219                                                                                                                                                                                                                                                    meters per second squared
#> 220                                                                                                                                                                                                                                       micromoles per square meter per second
#> 221                                                                                                                                                                                                                                                                     1/meters
#> 222                                                                                                                                                                                                                                             reciprocal of meter, or 1/meters
#> 223                                                                                                                                                                                                                                            also called reciprocal centimeter
#> 224                                                                                                                                                                                                                                                    cubic meters per kilogram
#> 225                                                                                                                                                                                                                                                   cubic micrometers per gram
#> 226                                                                                                                                                                                                                                                    cubic meters per kilogram
#> 227                                                                                                                                                                                                                                                   cubic micrometers per gram
#> 228                                                                                                                                                                                                                            ampere per meter squared, unit of current density
#> 229                                                                                                                                                                                                                            amperes per square meter, unit of current density
#> 230                                                                                                                                                                                                                                                             ampere per meter
#> 231                                                                                                                                                                                                                                                         mole per cubic meter
#> 232                                                                                                                                                                                                                                                       molarity = moles/liter
#> 233                                                                                                                                                                                                                                                        moles per cubic meter
#> 234                                                                                                                                                                                   moles per liter (perferred over molarity, as molarity refers only to dissolved substances)
#> 235                                                                                                                                                                                                                                                        millimoles per liter 
#> 236                                                                                                                                                                                                                                                         micromoles per liter
#> 237                                                                                                                                                                                                                                                          nanomoles per liter
#> 238                                                                                                                                                                                                                                                   millimoles per cubic meter
#> 239                                                                                                                                    concentration of charge (on dissolved ions). conversions must know the name of the ion; \n      a single multiplier to SI is not possible
#> 240                                                                                                                                    concentration of charge (on dissolved ions). conversions must know the name of the ion; \n      a single multiplier to SI is not possible
#> 241                                                                                                                                    concentration of charge (on dissolved ions). conversions must know the name of the ion; \n      a single multiplier to SI is not possible
#> 242                                                                                                                                                                                                                                                          molality = moles/kg
#> 243                                                                                                                                                                                                                                                          millimoles per gram
#> 244                                                                                                                                                                                                                                                               moles per gram
#> 245                                                                                                                                                                                                                                                           moles per kilogram
#> 246                                                                                                                                                                                                                                                          millimoles per gram
#> 247                                                                                                                                                                                                                                             candela Per Square Meter (1 lux)
#> 248                                                                                                                                                                                                                                             candela Per Square Meter (1 lux)
#> 249 meters squared per second, SI unit for kinematic viscosity, specific relative \n      angular momentum and thermal diffusivity. The unit may be better understood when phrased \n      as "meter per second times meter" (velocity of an object with respect to a position).
#> 250                                                                                                                                                                                                                                                       meters squared per day
#> 251                                                                                                                                                                                                                                                         feet squared per day
#> 252                                                                                                                                                                                                                                                          square feet per day
#> 253                                                                                                                                                                                                                                                        square meters per day
#> 254 meters squared per second, SI unit for kinematic viscosity, specific relative \n      angular momentum and thermal diffusivity. The unit may be better understood when phrased \n      as "meter per second times meter" (velocity of an object with respect to a position).
#> 255                                                                                                                                                                                                                                        kilograms per meter sqared per second
#> 256                                                                                                                                                                                                                                      grams Per Centimeter Squared Per Second
#> 257                                                                                                                                                                                                                                             grams Per Meter Squared Per Year
#> 258                                                                                                                                                                                                                                                    grams Per Hectare Per Day
#> 259                                                                                                                                                                                                                                               kilograms Per Hectare Per Year
#> 260                                                                                                                                                                                                                                         kilograms Per Meter Squared Per Year
#> 261                                                                                                                                                                                                                                       grams per square centimeter per second
#> 262                                                                                                                                                                                                                                            grams Per Hectare Squared Per Day
#> 263                                                                                                                                                                                                                                              grams per square meter per year
#> 264                                                                                                                                                                                                                                               kilograms Per Hectare Per Year
#> 265                                                                                                                                                                                                                                        kilograms per square meter per second
#> 266                                                                                                                                                                                                                                           kilograms per square meter per day
#> 267                                                                                                                                                                                                                                               grams per square meter per day
#> 268                                                                                                                                                                                                                                           milligram per square meter per day
#> 269                                                                                                                                                                                                                                          kilograms per square meter per year
#> 270                                                                                                                                                                                                                                                           moles per kilogram
#> 271                                                                                                                                                                                                                                                               moles per gram
#> 272                                                                                                                                                                                                                                                          millimoles per gram
#> 273                                                                                                                                                                                                                                                moles per kilogram per second
#> 274                                                                                                                                                                                                                                                nanomoles Per Gram Per Second
#> 275                                                                                                                                                                                                                                                moles per kilogram per second
#> 276                                                                                                                                                                                                                                                nanomoles Per Gram Per Second
#> 277                                                                                                                                                                                                                                                  nanomoles Per Gram Per Hour
#> 278                                                                                                                                                                                                                                                   nanomoles Per Gram Per day
#> 279                                                                                                                                                                                                                                               micromoles Per Gram Per Second
#> 280                                                                                                                                                                                                                                                 micromoles Per Gram Per Hour
#> 281                                                                                                                                                                                                                                                  micromoles Per Gram Per day
#> 282                                                                                                                                                                                                                                                         kilograms per second
#> 283                                                                                                                                                                                                                                                              tonnes Per Year
#> 284                                                                                                                                                                                                                                                               grams Per Year
#> 285                                                                                                                                                                                                                                                               grams Per Year
#> 286                                                                                                                                                                                                                                                         kilograms per second
#> 287                                                                                                                                                                                                                                                              tonnes Per Year
#> 288                                                                                                                                                                                                                    number per meter squared, e.g., for a population density.
#> 289                                                                                                                                                                                                                                                 number per kilometer squared
#> 290                                                                                                                                                                                                                                                           number per hectare
#> 291                                                                                                                                                                                                                                                       number per meter cubed
#> 292                                                                                                                                                                                                                                                 number of entities per liter
#> 293                                                                                                                                                                                                                                            number of entities per milliliter
#> 294                                                                                                                                                                                                                                                              meters per gram
#> 295                                                                                                                                                                                                                                                              meters per gram
#> 296                                                                                                                                                                                                                                                  number of entities per gram
#> 297                                                                                                                                                                                                                                                               grams per gram
#> 298                                                                                                                                                                                                                                                          micrograms per gram
#> 299                                                                                                                                                                                                                                                               grams per gram
#> 300                                                                                                                                                                                                                                                      milligrams per kilogram
#> 301                                                                                                                                                                                                                                                          micrograms per gram
#> 302                                                                                                                                                                                                                                                          micrograms per gram
#> 303                                                                                                                                                                                                                                                 micrograms per gram per hour
#> 304                                                                                                                                                                                                                                                  micrograms per gram per day
#> 305                                                                                                                                                                                                                                                 micrograms per gram per week
#> 306                                                                                                                                                                                                                                                 nanoograms per gram per hour
#> 307                                                                                                                                                                                                                                       cubic centimeters per cubic centimeter
#> 308                                                                                                                                                                                                                                                        milliliters per liter
#> 309                                                                                                                                                                                                                                                        milliliters per liter
#> 310                                                                                                                                                                                                                                                        milliliters per liter
#> 311                                                                                                                                                                                                                                                        milliliters per liter
#> 312                                                                                                                                                                                                                                                        milliliters per liter
#> 313                                                                                                                                                                                                                                                          millimoles per mole
#> 314                                                                                                                                                                                                                                                          millimoles per mole
#> 315                                                                                                                                                                                                                                                          millimoles per mole
#> 316                                                                                                                                                                                                                                                          millimoles per mole
#> 317                                                                                                                                                                                                                                                      micromoles per kilogram
#> 318                                                                                                                                                                                                                                                      micromoles per kilogram
#> 319                                                                                                                                                                                                                                                      micromoles per kilogram
#> 320                                                                                                                                                                                                                                                      micromoles per kilogram
#> 321                                                                                                                                                                                                        percent, one part per hundred parts. a decimal ratio multipled by 100
#> 322                                                                                                                                                                                                       permil, one part per thousand parts. a decimal ratio multipled by 1000
#> 323                                                                                                                                                                                                       watts per square meter, also, 1 kilogram per second cubed (ie, a flux)
#> 324                                                                                                                                                                                                                                                   kilowatts per square meter
#> 325                                                                                                                                                                                                                                     watts per square meter, in a solid angle
#> 326                                                                                                                                                                                                                                watts per square centimeter, in a solid angle
#> 327                                                                                                                                                                                                                               watts per square meter, per unit of wavelength
#> 328                                                                                                                                                                                                                          watts per square centimeter, per unit of wavelength
#> 329                                                                                                                                                                                                              watts per square meter, per unit of wavelength in a solid angle
#> 330                                                                                                                                                                                                   microwatts per square centimeter, per unit of wavelength, in a solid angle
#> 331                                                                                                                                                                                                                                       micromoles per square meter per second
#> 332                                                                                                                                                                                                                                       micromoles per square meter per second
#> 333                                                                                                                                                                                                                                  micromoles per square centimeter per second
#> 334                                                                                                                                                                                                                                          megajoules per square meter per day
#> 335                                                                                                                                                                                     Langley (Ly) per day. Ly is a unit of energy density = 41840 joule/m^2, = 1 calorie/cm^2
#>      abbreviation       multiplierToSI               deprecatedInFavorOf
#> 1            <NA>                 <NA>                              <NA>
#> 2             sec                    1                              <NA>
#> 3               m                    1                              <NA>
#> 4              kg                    1                              <NA>
#> 5               K                    1                              <NA>
#> 6               C                    1                              <NA>
#> 7               A                    1                              <NA>
#> 8             mol                    1                              <NA>
#> 9              cd                    1                              <NA>
#> 10           <NA>                 <NA>                              <NA>
#> 11             m³                    1                        meterCubed
#> 12           <NA>                   60                              <NA>
#> 13           <NA>                 3600                              <NA>
#> 14           <NA>                86400                              <NA>
#> 15           <NA>               604800                              <NA>
#> 16           <NA>             31536000                              <NA>
#> 17           <NA>             31622400                              <NA>
#> 18             ng       0.000000000001                              <NA>
#> 19             μg          0.000000001                              <NA>
#> 20             mg             0.000001                              <NA>
#> 21             cg              0.00001                              <NA>
#> 22             dg               0.0001                              <NA>
#> 23              g                0.001                              <NA>
#> 24            dag                 0.01                              <NA>
#> 25             hg                  0.1                              <NA>
#> 26             Mg                 1000                              <NA>
#> 27              T                 1000                              <NA>
#> 28            lbs               0.4536                              <NA>
#> 29            ton             907.1999                              <NA>
#> 30              C                    1                              <NA>
#> 31              F                0.556                              <NA>
#> 32             nm          0.000000001                              <NA>
#> 33             μm             0.000001                              <NA>
#> 34              μ             0.000001                        micrometer
#> 35             mm                0.001                              <NA>
#> 36             cm                 0.01                              <NA>
#> 37             dm                  0.1                              <NA>
#> 38            dam                   10                              <NA>
#> 39             hm                  100                              <NA>
#> 40             km                 1000                              <NA>
#> 41             Mm              1000000                              <NA>
#> 42              Å         0.0000000001                              <NA>
#> 43             in               0.0254                              <NA>
#> 44           usft            0.3048006                              <NA>
#> 45             ft               0.3048                              <NA>
#> 46           gcft            0.3047997                              <NA>
#> 47           <NA>               1.8288                              <NA>
#> 48           <NA>                 1852                              <NA>
#> 49           yard               0.9144                              <NA>
#> 50           <NA> 0.914398530744440774                              <NA>
#> 51           <NA>         0.2011661949                              <NA>
#> 52           <NA>  0.91439841461602867                              yard
#> 53           mile             1609.344                              <NA>
#> 54           nsec          0.000000001                              <NA>
#> 55           μsec             0.000001                              <NA>
#> 56           msec                0.001                              <NA>
#> 57           csec                 0.01                              <NA>
#> 58           dsec                  0.1                              <NA>
#> 59          dasec                   10                              <NA>
#> 60           hsec                  100                              <NA>
#> 61           ksec                 1000                              <NA>
#> 62           Msec              1000000                              <NA>
#> 63            min                   60                              <NA>
#> 64             hr                 3600                              <NA>
#> 65             kL                    1                              <NA>
#> 66             μl          0.000000001                              <NA>
#> 67             ml             0.000001                              <NA>
#> 68              L                0.001                              <NA>
#> 69            gal             3.785412                              <NA>
#> 70             qt             0.946353                              <NA>
#> 71              b             35.23907                              <NA>
#> 72            in³           0.01638706                         inchCubed
#> 73           pint             0.473176                              <NA>
#> 74             m³                    1                              <NA>
#> 75            cm³             0.000001                              <NA>
#> 76            in³           0.01638706                              <NA>
#> 77            rad                    1                              <NA>
#> 78              º         0.0174532924                              <NA>
#> 79           grad             0.015707                              <NA>
#> 80             sr                    1                              <NA>
#> 81            MHz              1000000                              <NA>
#> 82            KHz                 1000                              <NA>
#> 83             Hz                    1                              <NA>
#> 84            mHz                0.001                              <NA>
#> 85              N                    1                              <NA>
#> 86              J                    1                              <NA>
#> 87            cal               4.1868                              <NA>
#> 88            btu            1055.0559                              <NA>
#> 89           <NA>             1.355818                              <NA>
#> 90             Ly                41840                              <NA>
#> 91             lm                    1                              <NA>
#> 92             lx                    1                              <NA>
#> 93             Bq                    1                              <NA>
#> 94             Gy                    1                              <NA>
#> 95             Sv                    1                              <NA>
#> 96            kat                    1                              <NA>
#> 97              H                    1                              <NA>
#> 98             MW              1000000                              <NA>
#> 99             kW                 1000                              <NA>
#> 100             W                    1                              <NA>
#> 101            mW                0.001                              <NA>
#> 102            MV              1000000                              <NA>
#> 103            kV                 1000                              <NA>
#> 104             V                    1                              <NA>
#> 105            mV                0.001                              <NA>
#> 106             F                    1                              <NA>
#> 107             Ω                    1                              <NA>
#> 108            Ωm                    1                              <NA>
#> 109           S/m                    1                              <NA>
#> 110          S/cm                  .01                              <NA>
#> 111             S                    1                           siemens
#> 112             S                    1                              <NA>
#> 113            Wb                    1                              <NA>
#> 114             T                    1                              <NA>
#> 115            Pa                    1                              <NA>
#> 116           MPa              1000000                              <NA>
#> 117           kPa                 1000                              <NA>
#> 118           hPa                  100                              <NA>
#> 119           atm               101325                              <NA>
#> 120           bar               100000                              <NA>
#> 121          mbar                  100                              <NA>
#> 122          dbar                10000                              <NA>
#> 123         kg/m²                    1           kilogramPerMeterSquared
#> 124          g/m²                0.001               gramPerMeterSquared
#> 125         mg/m²             0.000001          milligramPerMeterSquared
#> 126          <NA>               0.0001                kilogramPerHectare
#> 127          <NA>                  0.1                              <NA>
#> 128       lbs/in²             703.0696               poundPerInchSquared
#> 129         g/cm²                   10                              <NA>
#> 130          g/m²                0.001                              <NA>
#> 131    kg/hectare               0.0001                              <NA>
#> 132         kg/m²                    1                              <NA>
#> 133         mg/m²             0.000001                              <NA>
#> 134       lb/acre 0.000112084667279431                              <NA>
#> 135       lbs/in²             703.0696                              <NA>
#> 136          <NA>                    1             kilogramPerMeterCubed
#> 137         kg/m³                    1            milligramPerMilliliter
#> 138           g/l                    1                      gramPerLiter
#> 139         mg/m³             0.000001            milligramPerMeterCubed
#> 140          μg/l             0.000001                 microgramPerLiter
#> 141          mg/l                0.001                 milligramPerLiter
#> 142         g/cm³                 1000            gramPerCentimeterCubed
#> 143          g/ml                 1000                 gramPerMilliliter
#> 144         g/cm³                 1000                              <NA>
#> 145           g/l                    1                              <NA>
#> 146          g/ml                 1000                              <NA>
#> 147          μg/l             0.000001                              <NA>
#> 148          mg/l                0.001                              <NA>
#> 149         mg/m³             0.000001                              <NA>
#> 150         kg/m³                    1                              <NA>
#> 151         Mg/m³                 1000                              <NA>
#> 152         mg/ml                    1                              <NA>
#> 153          <NA>                    1                gramPerDayPerLiter
#> 154       mg/m3/d         0.0000015741                              <NA>
#> 155         g/d/l                    1                              <NA>
#> 156           l/s                    1                    literPerSecond
#> 157          m³/s                 1000               meterCubedPerSecond
#> 158         ft³/s            28.316874                footCubedPerSecond
#> 159         ft³/s            28.316874                              <NA>
#> 160           l/s                    1                              <NA>
#> 161          m³/s                 1000                              <NA>
#> 162            m²                    1                      meterSquared
#> 163             a                  100                              <NA>
#> 164            ha                10000                              <NA>
#> 165          <NA>              1000000                  kilometerSquared
#> 166          <NA>             0.000001                 millimeterSquared
#> 167          <NA>               0.0001                 centimeterSquared
#> 168             a            4046.8564                              <NA>
#> 169           ft²             0.092903                       footSquared
#> 170           yd²             0.836131                       yardSquared
#> 171         mile²        2589998.49806                       mileSquared
#> 172           cm²               0.0001                              <NA>
#> 173           ft²             0.092903                              <NA>
#> 174           km²              1000000                              <NA>
#> 175            m²                    1                              <NA>
#> 176         mile²        2589998.49806                              <NA>
#> 177           mm²             0.000001                              <NA>
#> 178           yd²             0.836131                              <NA>
#> 179          l/m²                    1              literPerMeterSquared
#> 180          <NA>              0.00870                     bushelPerAcre
#> 181          <NA>               0.0001                   literPerHectare
#> 182       bu/acre              0.00870                              <NA>
#> 183     l/hectare               0.0001                              <NA>
#> 184          l/m²                    1                              <NA>
#> 185         m3/ha               0.0001                              <NA>
#> 186       m^3/m^2                    1                              <NA>
#> 187        m^2/ha               0.0001                              <NA>
#> 188         m²/kg                    1           meterSquaredPerKilogram
#> 189         m²/kg                    1                              <NA>
#> 190           m/s                    1                    meterPerSecond
#> 191         m/day          .0000115741                       meterPerDay
#> 192        ft/day        0.00000352778                        footPerDay
#> 193          ft/s               0.3048                     footPerSecond
#> 194         ft/hr          0.000084667                       footPerHour
#> 195          yd/s               0.9144                     yardPerSecond
#> 196           mph              0.44704                       milePerHour
#> 197           mps             1609.344                     milePerSecond
#> 198           mpm              26.8224                     milePerMinute
#> 199          cm/s                 0.01               centimeterPerSecond
#> 200          mm/s                0.001               millimeterPerSecond
#> 201       cm/year    0.000000000317098                 centimeterPerYear
#> 202          <NA>             0.514444                              knot
#> 203         km/hr               0.2778                  kilometerPerHour
#> 204          cm/s                 0.01                              <NA>
#> 205        ft/day        0.00000352778                              <NA>
#> 206         ft/hr          0.000084667                              <NA>
#> 207          ft/s               0.3048                              <NA>
#> 208         in/hr        0.00000705556                              <NA>
#> 209         km/hr               0.2778                              <NA>
#> 210          knot    0.514444444444444                              <NA>
#> 211         m/day          .0000115741                              <NA>
#> 212           m/s                    1                              <NA>
#> 213           mph              0.44704                              <NA>
#> 214           mpm              26.8224                              <NA>
#> 215           mps             1609.344                              <NA>
#> 216          mm/d     0.00000001157407                              <NA>
#> 217          mm/s                0.001                              <NA>
#> 218          yd/s               0.9144                              <NA>
#> 219          m/s²                    1             meterPerSecondSquared
#> 220          m/s²                    1                              <NA>
#> 221          <NA>                    1                      inverseMeter
#> 222          <NA>                    1                              <NA>
#> 223          <NA>                  .01                              <NA>
#> 224         m³/kg                    1             meterCubedPerKilogram
#> 225        μm³/kg    0.000000000000001            micrometerCubedPerGram
#> 226         m³/kg                    1                              <NA>
#> 227        μm³/kg    0.000000000000001                              <NA>
#> 228          A/m²                    1             amperePerMeterSquared
#> 229          A/m²                    1                              <NA>
#> 230           A/m                    1                              <NA>
#> 231          <NA>                    1                 molePerMeterCubed
#> 232             M                 1000                      molePerLiter
#> 233        mol/m³                    1                              <NA>
#> 234         mol/l                 1000                              <NA>
#> 235        mmol/l                    1                              <NA>
#> 236        µmol/l                0.001                              <NA>
#> 237        nmol/l             0.000001                              <NA>
#> 238        mol/m³                 .001                              <NA>
#> 239           E/l                 <NA>                              <NA>
#> 240          mE/l                 <NA>                              <NA>
#> 241          µE/l                 <NA>                              <NA>
#> 242             m                    1                   molePerKilogram
#> 243        mmol/g                    1                              <NA>
#> 244         mol/g                 1000                              <NA>
#> 245        mol/kg                    1                              <NA>
#> 246        umol/g                0.001                              <NA>
#> 247         cd/m²                    1            candelaPerMeterSquared
#> 248         cd/m²                    1                              <NA>
#> 249          m²/s                    1             meterSquaredPerSecond
#> 250        m²/day        0.00001157407                meterSquaredPerDay
#> 251       ft²/day       0.000001075267                 footSquaredPerDay
#> 252         ft²/d       0.000001075267                              <NA>
#> 253          m²/d        0.00001157407                              <NA>
#> 254          m²/s                    1                              <NA>
#> 255          <NA>                    1  kilogramPerMeterSquaredPerSecond
#> 256          <NA>                   10 gramPerCentimeterSquaredPerSecond
#> 257          <NA>   0.0000000000317098        gramPerMeterSquaredPerYear
#> 258          <NA>   0.0000000000011574              gramPerDayPerHectare
#> 259          <NA> 0.000000000003170979         kilogramPerHectarePerYear
#> 260          <NA>     0.00000003170979    kilogramPerMeterSquaredPerYear
#> 261       g/cm²/s                   10                              <NA>
#> 262   g/d/hectare 0.000000000001157407                              <NA>
#> 263       g/m²/yr  0.00000000003170979                              <NA>
#> 264 kg/hectare/yr 0.000000000003170979                              <NA>
#> 265       kg/m²/s                    1                              <NA>
#> 266       kg/m²/d          0.000015741                              <NA>
#> 267       kg/m²/d       0.000000015741                              <NA>
#> 268       mg/m²/d    0.000000000015741                              <NA>
#> 269      kg/m²/yr     0.00000003170979                              <NA>
#> 270          <NA>                    1                   molePerKilogram
#> 271          <NA>                 1000                       molePerGram
#> 272          <NA>                    1                  millimolePerGram
#> 273          <NA>                    1          molePerKilogramPerSecond
#> 274          <NA>             0.000001          nanomolePerGramPerSecond
#> 275      mol/kg/s                    1                              <NA>
#> 276      nmol/g/s             0.000001                              <NA>
#> 277      nmol/g/h    0.000000000277778                              <NA>
#> 278      nmol/g/d   0.0000000000115741                              <NA>
#> 279      nmol/g/s                0.001                              <NA>
#> 280      nmol/g/h       0.000000277778                              <NA>
#> 281      nmol/g/d      0.0000000115741                              <NA>
#> 282          kg/s                    1                 kilogramPerSecond
#> 283          <NA>            0.0000317                      tonnePerYear
#> 284          g/yr      0.0000000000317                       gramPerYear
#> 285          g/yr  0.00000000003170979                              <NA>
#> 286          kg/s                    1                              <NA>
#> 287          t/yr        0.00003170979                              <NA>
#> 288          <NA>                    1                              <NA>
#> 289          <NA>             0.000001                              <NA>
#> 290     #/hectare               0.0001                              <NA>
#> 291          <NA>                    1                              <NA>
#> 292          <NA>                 1000                              <NA>
#> 293          <NA>              1000000                              <NA>
#> 294           m/g                    1                      meterPerGram
#> 295           m/g                    1                              <NA>
#> 296          <NA>                    1                              <NA>
#> 297          <NA>                    1                       gramPerGram
#> 298          <NA>             0.000001                  microgramPerGram
#> 299           g/g                    1                              <NA>
#> 300         mg/kg             0.000001                              <NA>
#> 301          μg/g             0.000001                              <NA>
#> 302          ng/g          0.000000001                              <NA>
#> 303        μg/g/h    0.000000000277778                              <NA>
#> 304      μg/g/day   0.0000000000115741                              <NA>
#> 305     μg/g/week  0.00000000000165344                              <NA>
#> 306          ng/g       0.000000277778                              <NA>
#> 307          <NA>                    1           meterCubedPerMeterCubed
#> 308         m³/m³                    1                              <NA>
#> 309           l/l                    1                              <NA>
#> 310          ml/l                0.001                              <NA>
#> 311          μl/l             0.000001                              <NA>
#> 312          nl/l          0.000000001                              <NA>
#> 313       mol/mol                    1                              <NA>
#> 314      mmol/mol                 .001                              <NA>
#> 315      μmol/mol              .000001                              <NA>
#> 316      nmol/mol           .000000001                              <NA>
#> 317        mol/kg                    1                              <NA>
#> 318       mmol/kg                0.001                              <NA>
#> 319       µmol/kg             0.000001                              <NA>
#> 320       nmol/kg          0.000000001                              <NA>
#> 321             %                    1                              <NA>
#> 322          o/oo                    1                              <NA>
#> 323          W/m²                    1                              <NA>
#> 324         kW/m²                 1000                              <NA>
#> 325       W/m²/sr                    1                              <NA>
#> 326     µW/cm²/sr            0.0000001                              <NA>
#> 327       W/m²/nm          0.000000001                              <NA>
#> 328     µW/cm²/nm            0.0000001                              <NA>
#> 329    W/m²/nm/sr          0.000000001                              <NA>
#> 330  µW/cm²/nm/sr            0.0000001                              <NA>
#> 331      mol/m²/s                    1                              <NA>
#> 332     µmol/m²/s             0.000001                              <NA>
#> 333    µmol/cm²/s                 0.01                              <NA>
#> 334     MJ/m2/day              11.5741                              <NA>
#> 335        Ly/day             0.484259                              <NA>
#>                                    parentSI constantToSI
#> 1                                      <NA>         <NA>
#> 2                                      <NA>         <NA>
#> 3                                      <NA>         <NA>
#> 4                                      <NA>         <NA>
#> 5                                      <NA>         <NA>
#> 6                                      <NA>         <NA>
#> 7                                      <NA>         <NA>
#> 8                                      <NA>         <NA>
#> 9                                      <NA>         <NA>
#> 10                                     <NA>         <NA>
#> 11                                     <NA>         <NA>
#> 12                                   second         <NA>
#> 13                                   second         <NA>
#> 14                                   second         <NA>
#> 15                                   second         <NA>
#> 16                                   second         <NA>
#> 17                                   second         <NA>
#> 18                                 kilogram         <NA>
#> 19                                 kilogram         <NA>
#> 20                                 kilogram         <NA>
#> 21                                 kilogram         <NA>
#> 22                                 kilogram         <NA>
#> 23                                 kilogram         <NA>
#> 24                                 kilogram         <NA>
#> 25                                 kilogram         <NA>
#> 26                                 kilogram         <NA>
#> 27                                 kilogram         <NA>
#> 28                                 kilogram         <NA>
#> 29                                 kilogram         <NA>
#> 30                                   kelvin       273.18
#> 31                                   kelvin      255.402
#> 32                                    meter         <NA>
#> 33                                    meter         <NA>
#> 34                                    meter         <NA>
#> 35                                    meter         <NA>
#> 36                                    meter         <NA>
#> 37                                    meter         <NA>
#> 38                                    meter         <NA>
#> 39                                    meter         <NA>
#> 40                                    meter         <NA>
#> 41                                    meter         <NA>
#> 42                                    meter         <NA>
#> 43                                    meter         <NA>
#> 44                                    meter         <NA>
#> 45                                    meter         <NA>
#> 46                                    meter         <NA>
#> 47                                    meter         <NA>
#> 48                                    meter         <NA>
#> 49                                    meter         <NA>
#> 50                                    meter         <NA>
#> 51                                    meter         <NA>
#> 52                                    meter         <NA>
#> 53                                    meter         <NA>
#> 54                                   second         <NA>
#> 55                                   second         <NA>
#> 56                                   second         <NA>
#> 57                                   second         <NA>
#> 58                                   second         <NA>
#> 59                                   second         <NA>
#> 60                                   second         <NA>
#> 61                                   second         <NA>
#> 62                                   second         <NA>
#> 63                                   second         <NA>
#> 64                                   second         <NA>
#> 65                               cubicMeter         <NA>
#> 66                               cubicMeter         <NA>
#> 67                               cubicMeter         <NA>
#> 68                               cubicMeter         <NA>
#> 69                                    liter         <NA>
#> 70                                    liter         <NA>
#> 71                                    liter         <NA>
#> 72                                    liter         <NA>
#> 73                                    liter         <NA>
#> 74                               meterCubed         <NA>
#> 75                               meterCubed         <NA>
#> 76                                    liter         <NA>
#> 77                                     <NA>         <NA>
#> 78                                   radian         <NA>
#> 79                                   radian         <NA>
#> 80                                     <NA>         <NA>
#> 81                                    hertz         <NA>
#> 82                                    hertz         <NA>
#> 83                                     <NA>         <NA>
#> 84                                    hertz         <NA>
#> 85                                     <NA>         <NA>
#> 86                                     <NA>         <NA>
#> 87                                    joule         <NA>
#> 88                                    joule         <NA>
#> 89                                    joule         <NA>
#> 90                     joulePerMeterSquared            0
#> 91                                     <NA>         <NA>
#> 92                                     <NA>         <NA>
#> 93                                     <NA>         <NA>
#> 94                                     <NA>         <NA>
#> 95                                     <NA>         <NA>
#> 96                                     <NA>         <NA>
#> 97                                     <NA>         <NA>
#> 98                                     watt         <NA>
#> 99                                     watt         <NA>
#> 100                                    <NA>         <NA>
#> 101                                    watt         <NA>
#> 102                                    volt         <NA>
#> 103                                    volt         <NA>
#> 104                                    <NA>         <NA>
#> 105                                    volt         <NA>
#> 106                                    <NA>         <NA>
#> 107                                    <NA>         <NA>
#> 108                                    <NA>         <NA>
#> 109                         siemensPerMeter         <NA>
#> 110                         siemensPerMeter         <NA>
#> 111                                    <NA>         <NA>
#> 112                                 siemens         <NA>
#> 113                                    <NA>         <NA>
#> 114                                    <NA>         <NA>
#> 115                                    <NA>         <NA>
#> 116                                  pascal         <NA>
#> 117                                  pascal         <NA>
#> 118                                  pascal         <NA>
#> 119                                  pascal         <NA>
#> 120                                  pascal         <NA>
#> 121                                  pascal         <NA>
#> 122                                  pascal         <NA>
#> 123                                    <NA>         <NA>
#> 124                 kilogramPerMeterSquared         <NA>
#> 125                 kilogramPerMeterSquared         <NA>
#> 126                 kilogramPerMeterSquared         <NA>
#> 127                 kilogramPerMeterSquared         <NA>
#> 128                 kilogramPerMeterSquared         <NA>
#> 129                 kilogramPerMeterSquared         <NA>
#> 130                 kilogramPerMeterSquared         <NA>
#> 131                 kilogramPerMeterSquared         <NA>
#> 132                 kilogramPerMeterSquared         <NA>
#> 133                 kilogramPerMeterSquared         <NA>
#> 134                 kilogramPerMeterSquared         <NA>
#> 135                 kilogramPerMeterSquared         <NA>
#> 136                                    <NA>         <NA>
#> 137                   kilogramPerMeterCubed         <NA>
#> 138                   kilogramPerMeterCubed         <NA>
#> 139                   kilogramPerMeterCubed         <NA>
#> 140                   kilogramPerMeterCubed         <NA>
#> 141                   kilogramPerMeterCubed         <NA>
#> 142                   kilogramPerMeterCubed         <NA>
#> 143                   kilogramPerMeterCubed         <NA>
#> 144                   kilogramPerMeterCubed         <NA>
#> 145                   kilogramPerMeterCubed         <NA>
#> 146                   kilogramPerMeterCubed         <NA>
#> 147                   kilogramPerMeterCubed         <NA>
#> 148                   kilogramPerMeterCubed         <NA>
#> 149                   kilogramPerMeterCubed         <NA>
#> 150                   kilogramPerMeterCubed         <NA>
#> 151                   kilogramPerMeterCubed         <NA>
#> 152                   kilogramPerMeterCubed         <NA>
#> 153                                    <NA>         <NA>
#> 154          kilogramPerMeterCubedPerSecond         <NA>
#> 155                      gramPerDayPerLiter         <NA>
#> 156                                    <NA>         <NA>
#> 157                          literPerSecond         <NA>
#> 158                          literPerSecond         <NA>
#> 159                          literPerSecond         <NA>
#> 160                          literPerSecond         <NA>
#> 161                          literPerSecond         <NA>
#> 162                                    <NA>         <NA>
#> 163                             squareMeter         <NA>
#> 164                             squareMeter         <NA>
#> 165                             squareMeter         <NA>
#> 166                             squareMeter         <NA>
#> 167                             squareMeter         <NA>
#> 168                             squareMeter         <NA>
#> 169                             squareMeter         <NA>
#> 170                             squareMeter         <NA>
#> 171                             squareMeter         <NA>
#> 172                            meterSquared         <NA>
#> 173                            meterSquared         <NA>
#> 174                            meterSquared         <NA>
#> 175                            meterSquared         <NA>
#> 176                            meterSquared         <NA>
#> 177                            meterSquared         <NA>
#> 178                            meterSquared         <NA>
#> 179                                    <NA>         <NA>
#> 180                    literPerMeterSquared         <NA>
#> 181                    literPerMeterSquared         <NA>
#> 182                    literPerMeterSquared         <NA>
#> 183                    literPerMeterSquared         <NA>
#> 184                    literPerMeterSquared         <NA>
#> 185               meterCubedPerMeterSquared         <NA>
#> 186               meterCubedPerMeterSquared         <NA>
#> 187             meterSquaredPerMeterSquared         <NA>
#> 188                                    <NA>         <NA>
#> 189                 meterSquaredPerKilogram         <NA>
#> 190                          meterPerSecond         <NA>
#> 191                                    <NA>         <NA>
#> 192                          meterPerSecond         <NA>
#> 193                          meterPerSecond         <NA>
#> 194                          meterPerSecond         <NA>
#> 195                          meterPerSecond         <NA>
#> 196                          meterPerSecond         <NA>
#> 197                          meterPerSecond         <NA>
#> 198                          meterPerSecond         <NA>
#> 199                          meterPerSecond         <NA>
#> 200                          meterPerSecond         <NA>
#> 201                          meterPerSecond         <NA>
#> 202                          meterPerSecond         <NA>
#> 203                          meterPerSecond         <NA>
#> 204                          meterPerSecond         <NA>
#> 205                          meterPerSecond         <NA>
#> 206                          meterPerSecond         <NA>
#> 207                          meterPerSecond         <NA>
#> 208                          meterPerSecond         <NA>
#> 209                          meterPerSecond         <NA>
#> 210                          meterPerSecond         <NA>
#> 211                          meterPerSecond         <NA>
#> 212                          meterPerSecond         <NA>
#> 213                          meterPerSecond         <NA>
#> 214                          meterPerSecond         <NA>
#> 215                          meterPerSecond         <NA>
#> 216                          meterPerSecond         <NA>
#> 217                          meterPerSecond         <NA>
#> 218                          meterPerSecond         <NA>
#> 219                                    <NA>         <NA>
#> 220                   meterPerSecondSquared         <NA>
#> 221                                    <NA>         <NA>
#> 222                                    <NA>         <NA>
#> 223                                    <NA>         <NA>
#> 224                                    <NA>         <NA>
#> 225                   cubicMeterPerKilogram         <NA>
#> 226                   meterCubedPerKilogram         <NA>
#> 227                   meterCubedPerKilogram         <NA>
#> 228                                    <NA>         <NA>
#> 229                   amperePerMeterSquared         <NA>
#> 230                                    <NA>         <NA>
#> 231                                    <NA>         <NA>
#> 232                       molePerMeterCubed         <NA>
#> 233                       molePerMeterCubed         <NA>
#> 234                       molePerMeterCubed         <NA>
#> 235                       molePerMeterCubed         <NA>
#> 236                       molePerMeterCubed         <NA>
#> 237                       molePerMeterCubed         <NA>
#> 238                       molePerMeterCubed         <NA>
#> 239                       molePerMeterCubed         <NA>
#> 240                       molePerMeterCubed         <NA>
#> 241                       molePerMeterCubed         <NA>
#> 242                                    <NA>         <NA>
#> 243                         molePerKilogram         <NA>
#> 244                         molePerKilogram         <NA>
#> 245                         molePerKilogram         <NA>
#> 246                         molePerKilogram         <NA>
#> 247                                    <NA>         <NA>
#> 248                  candelaPerMeterSquared         <NA>
#> 249                                    <NA>         <NA>
#> 250                  metersSquaredPerSecond         <NA>
#> 251                  metersSquaredPerSecond         <NA>
#> 252                   meterSquaredPerSecond         <NA>
#> 253                   meterSquaredPerSecond         <NA>
#> 254                   meterSquaredPerSecond         <NA>
#> 255                                    <NA>         <NA>
#> 256        kilogramPerMeterSquaredPerSecond         <NA>
#> 257        kilogramPerMeterSquaredPerSecond         <NA>
#> 258        kilogramPerMeterSquaredPerSecond         <NA>
#> 259        kilogramPerMeterSquaredPerSecond         <NA>
#> 260        kilogramPerMeterSquaredPerSecond         <NA>
#> 261        kilogramPerMeterSquaredPerSecond         <NA>
#> 262        kilogramPerMeterSquaredPerSecond         <NA>
#> 263        kilogramPerMeterSquaredPerSecond         <NA>
#> 264        kilogramPerMeterSquaredPerSecond         <NA>
#> 265        kilogramPerMeterSquaredPerSecond         <NA>
#> 266        kilogramPerMeterSquaredPerSecond         <NA>
#> 267        kilogramPerMeterSquaredPerSecond         <NA>
#> 268        kilogramPerMeterSquaredPerSecond         <NA>
#> 269        kilogramPerMeterSquaredPerSecond         <NA>
#> 270                                    <NA>         <NA>
#> 271                         molePerKilogram         <NA>
#> 272                         molePerKilogram         <NA>
#> 273                                    <NA>         <NA>
#> 274                molePerKilogramPerSecond         <NA>
#> 275                molePerKilogramPerSecond         <NA>
#> 276                molePerKilogramPerSecond         <NA>
#> 277                molePerKilogramPerSecond         <NA>
#> 278                molePerKilogramPerSecond         <NA>
#> 279                molePerKilogramPerSecond         <NA>
#> 280                molePerKilogramPerSecond         <NA>
#> 281                molePerKilogramPerSecond         <NA>
#> 282                                    <NA>         <NA>
#> 283                       kilogramPerSecond         <NA>
#> 284                       kilogramPerSecond         <NA>
#> 285                       kilogramPerSecond         <NA>
#> 286                       kilogramPerSecond         <NA>
#> 287                       kilogramPerSecond         <NA>
#> 288                                    <NA>         <NA>
#> 289                   numberPerMeterSquared         <NA>
#> 290                   numberPerMeterSquared         <NA>
#> 291                                    <NA>         <NA>
#> 292                     numberPerMeterCubed         <NA>
#> 293                     numberPerMeterCubed         <NA>
#> 294                                    <NA>         <NA>
#> 295                            meterPerGram         <NA>
#> 296                                    <NA>         <NA>
#> 297                                    <NA>         <NA>
#> 298                            gramsPerGram         <NA>
#> 299                             gramPerGram         <NA>
#> 300                             gramPerGram         <NA>
#> 301                             gramPerGram         <NA>
#> 302                             gramPerGram         <NA>
#> 303                    gramPerGramPerSecond         <NA>
#> 304                    gramPerGramPerSecond         <NA>
#> 305                    gramPerGramPerSecond         <NA>
#> 306                    gramPerGramPerSecond         <NA>
#> 307                                    <NA>         <NA>
#> 308                 meterCubedPerMeterCubed         <NA>
#> 309                 meterCubedPerMeterCubed         <NA>
#> 310                 meterCubedPerMeterCubed         <NA>
#> 311                 meterCubedPerMeterCubed         <NA>
#> 312                 meterCubedPerMeterCubed         <NA>
#> 313                             molePerMole         <NA>
#> 314                             molePerMole         <NA>
#> 315                             molePerMole         <NA>
#> 316                             molePerMole         <NA>
#> 317                         molePerKilogram         <NA>
#> 318                         molePerKilogram         <NA>
#> 319                         molePerKilogram         <NA>
#> 320                         molePerKilogram         <NA>
#> 321                           dimensionless         <NA>
#> 322                           dimensionless         <NA>
#> 323                     wattPerMeterSquared         <NA>
#> 324                     wattPerMeterSquared         <NA>
#> 325         wattPerMeterSquaredPerSteradian         <NA>
#> 326         wattPerMeterSquaredPerSteradian         <NA>
#> 327             wattPerMeterSquaredPerMeter         <NA>
#> 328             wattPerMeterSquaredPerMeter         <NA>
#> 329 wattPerMeterSquaredPerMeterPerSteradian         <NA>
#> 330 wattPerMeterSquaredPerMeterPerSteradian         <NA>
#> 331            molePerMeterSquaredPerSecond         <NA>
#> 332            molePerMeterSquaredPerSecond         <NA>
#> 333            molePerMeterSquaredPerSecond         <NA>
#> 334           joulePerMeterSquaredPerSecond            0
#> 335           joulePerMeterSquaredPerSecond            0
#> 
#> $unitTypes
#>                                 id                           name     dimension
#> 1                     acceleration                   acceleration        length
#> 2                     acceleration                   acceleration        length
#> 3                     acceleration                   acceleration          time
#> 4                     acceleration                   acceleration          time
#> 5                           charge                         charge       current
#> 6                           charge                         charge       current
#> 7                           charge                         charge          time
#> 8                           charge                         charge          time
#> 9            magneticFieldStrength          magneticFieldStrength       current
#> 10           magneticFieldStrength          magneticFieldStrength       current
#> 11           magneticFieldStrength          magneticFieldStrength        length
#> 12           magneticFieldStrength          magneticFieldStrength        length
#> 13                  currentDensity                 currentDensity       current
#> 14                  currentDensity                 currentDensity       current
#> 15                  currentDensity                 currentDensity        length
#> 16                  currentDensity                 currentDensity        length
#> 17                  volumetricArea                 volumetricArea        length
#> 18                  volumetricArea                 volumetricArea        length
#> 19                  volumetricArea                 volumetricArea        length
#> 20                  volumetricArea                 volumetricArea        length
#> 21                           speed                          speed        length
#> 22                           speed                          speed        length
#> 23                           speed                          speed          time
#> 24                           speed                          speed          time
#> 25                     massDensity                    massDensity          mass
#> 26                     massDensity                    massDensity          mass
#> 27                     massDensity                    massDensity        length
#> 28                     massDensity                    massDensity        length
#> 29                     massPerMass                    massPerMass          mass
#> 30                     massPerMass                    massPerMass          mass
#> 31                     massPerMass                    massPerMass          mass
#> 32                     massPerMass                    massPerMass          mass
#> 33                 massPerMassRate                massPerMassRate          mass
#> 34                 massPerMassRate                massPerMassRate          mass
#> 35                 massPerMassRate                massPerMassRate          mass
#> 36                 massPerMassRate                massPerMassRate          mass
#> 37                 massPerMassRate                massPerMassRate          mass
#> 38                 massPerMassRate                massPerMassRate          mass
#> 39                 massPerMassRate                massPerMassRate          time
#> 40                 massPerMassRate                massPerMassRate          time
#> 41                 massPerMassRate                massPerMassRate          time
#> 42                 volumePerVolume                volumePerVolume        length
#> 43                 volumePerVolume                volumePerVolume        length
#> 44                 volumePerVolume                volumePerVolume          mass
#> 45                 volumePerVolume                volumePerVolume          mass
#> 46                  volumetricRate                 volumetricRate        length
#> 47                  volumetricRate                 volumetricRate        length
#> 48                  volumetricRate                 volumetricRate          time
#> 49                  volumetricRate                 volumetricRate          time
#> 50       volumetricMassDensityRate      volumetricMassDensityRate          mass
#> 51       volumetricMassDensityRate      volumetricMassDensityRate          mass
#> 52       volumetricMassDensityRate      volumetricMassDensityRate          mass
#> 53       volumetricMassDensityRate      volumetricMassDensityRate        length
#> 54       volumetricMassDensityRate      volumetricMassDensityRate        length
#> 55       volumetricMassDensityRate      volumetricMassDensityRate        length
#> 56       volumetricMassDensityRate      volumetricMassDensityRate          time
#> 57       volumetricMassDensityRate      volumetricMassDensityRate          time
#> 58       volumetricMassDensityRate      volumetricMassDensityRate          time
#> 59                        massFlux                       massFlux          mass
#> 60                        massFlux                       massFlux          mass
#> 61                        massFlux                       massFlux          mass
#> 62                        massFlux                       massFlux        length
#> 63                        massFlux                       massFlux        length
#> 64                        massFlux                       massFlux        length
#> 65                        massFlux                       massFlux          time
#> 66                        massFlux                       massFlux          time
#> 67                        massFlux                       massFlux          time
#> 68                  specificVolume                 specificVolume          mass
#> 69                  specificVolume                 specificVolume          mass
#> 70                  specificVolume                 specificVolume        length
#> 71                  specificVolume                 specificVolume        length
#> 72  amountOfSubstanceConcentration amountOfSubstanceConcentration        amount
#> 73  amountOfSubstanceConcentration amountOfSubstanceConcentration        amount
#> 74  amountOfSubstanceConcentration amountOfSubstanceConcentration        length
#> 75  amountOfSubstanceConcentration amountOfSubstanceConcentration        length
#> 76         amountOfSubstanceWeight        amountOfSubstanceWeight        amount
#> 77         amountOfSubstanceWeight        amountOfSubstanceWeight        amount
#> 78         amountOfSubstanceWeight        amountOfSubstanceWeight          mass
#> 79         amountOfSubstanceWeight        amountOfSubstanceWeight          mass
#> 80     amountOfSubstanceWeightRate    amountOfSubstanceWeightRate        amount
#> 81     amountOfSubstanceWeightRate    amountOfSubstanceWeightRate        amount
#> 82     amountOfSubstanceWeightRate    amountOfSubstanceWeightRate        amount
#> 83     amountOfSubstanceWeightRate    amountOfSubstanceWeightRate          mass
#> 84     amountOfSubstanceWeightRate    amountOfSubstanceWeightRate          mass
#> 85     amountOfSubstanceWeightRate    amountOfSubstanceWeightRate          mass
#> 86     amountOfSubstanceWeightRate    amountOfSubstanceWeightRate          time
#> 87     amountOfSubstanceWeightRate    amountOfSubstanceWeightRate          time
#> 88     amountOfSubstanceWeightRate    amountOfSubstanceWeightRate          time
#> 89                        massRate                       massRate          mass
#> 90                        massRate                       massRate          mass
#> 91                        massRate                       massRate          time
#> 92                        massRate                       massRate          time
#> 93                       luminance                      luminance    luminosity
#> 94                       luminance                      luminance    luminosity
#> 95                       luminance                      luminance        length
#> 96                       luminance                      luminance        length
#> 97               volumetricDensity              volumetricDensity dimensionless
#> 98               volumetricDensity              volumetricDensity dimensionless
#> 99               volumetricDensity              volumetricDensity        length
#> 100              volumetricDensity              volumetricDensity        length
#> 101                   arealDensity                   arealDensity dimensionless
#> 102                   arealDensity                   arealDensity dimensionless
#> 103                   arealDensity                   arealDensity        length
#> 104                   arealDensity                   arealDensity        length
#> 105               arealMassDensity               arealMassDensity          mass
#> 106               arealMassDensity               arealMassDensity          mass
#> 107               arealMassDensity               arealMassDensity        length
#> 108               arealMassDensity               arealMassDensity        length
#> 109                   specificArea                   specificArea          mass
#> 110                   specificArea                   specificArea          mass
#> 111                   specificArea                   specificArea        length
#> 112                   specificArea                   specificArea        length
#> 113                          force                          force          mass
#> 114                          force                          force          mass
#> 115                          force                          force          mass
#> 116                          force                          force        length
#> 117                          force                          force        length
#> 118                          force                          force        length
#> 119                          force                          force          time
#> 120                          force                          force          time
#> 121                          force                          force          time
#> 122                         energy                         energy          mass
#> 123                         energy                         energy          mass
#> 124                         energy                         energy          mass
#> 125                         energy                         energy        length
#> 126                         energy                         energy        length
#> 127                         energy                         energy        length
#> 128                         energy                         energy          time
#> 129                         energy                         energy          time
#> 130                         energy                         energy          time
#> 131                          power                          power          mass
#> 132                          power                          power          mass
#> 133                          power                          power          mass
#> 134                          power                          power        length
#> 135                          power                          power        length
#> 136                          power                          power        length
#> 137                          power                          power          time
#> 138                          power                          power          time
#> 139                          power                          power          time
#> 140            potentialDifference            potentialDifference          mass
#> 141            potentialDifference            potentialDifference          mass
#> 142            potentialDifference            potentialDifference          mass
#> 143            potentialDifference            potentialDifference          mass
#> 144            potentialDifference            potentialDifference        length
#> 145            potentialDifference            potentialDifference        length
#> 146            potentialDifference            potentialDifference        length
#> 147            potentialDifference            potentialDifference        length
#> 148            potentialDifference            potentialDifference          time
#> 149            potentialDifference            potentialDifference          time
#> 150            potentialDifference            potentialDifference          time
#> 151            potentialDifference            potentialDifference          time
#> 152            potentialDifference            potentialDifference       current
#> 153            potentialDifference            potentialDifference       current
#> 154            potentialDifference            potentialDifference       current
#> 155            potentialDifference            potentialDifference       current
#> 156                    capacitance                    capacitance          mass
#> 157                    capacitance                    capacitance          mass
#> 158                    capacitance                    capacitance          mass
#> 159                    capacitance                    capacitance          mass
#> 160                    capacitance                    capacitance        length
#> 161                    capacitance                    capacitance        length
#> 162                    capacitance                    capacitance        length
#> 163                    capacitance                    capacitance        length
#> 164                    capacitance                    capacitance          time
#> 165                    capacitance                    capacitance          time
#> 166                    capacitance                    capacitance          time
#> 167                    capacitance                    capacitance          time
#> 168                    capacitance                    capacitance       current
#> 169                    capacitance                    capacitance       current
#> 170                    capacitance                    capacitance       current
#> 171                    capacitance                    capacitance       current
#> 172                     resistance                     resistance          mass
#> 173                     resistance                     resistance          mass
#> 174                     resistance                     resistance          mass
#> 175                     resistance                     resistance          mass
#> 176                     resistance                     resistance        length
#> 177                     resistance                     resistance        length
#> 178                     resistance                     resistance        length
#> 179                     resistance                     resistance        length
#> 180                     resistance                     resistance          time
#> 181                     resistance                     resistance          time
#> 182                     resistance                     resistance          time
#> 183                     resistance                     resistance          time
#> 184                     resistance                     resistance       current
#> 185                     resistance                     resistance       current
#> 186                     resistance                     resistance       current
#> 187                     resistance                     resistance       current
#> 188                    resistivity                    resistivity          mass
#> 189                    resistivity                    resistivity          mass
#> 190                    resistivity                    resistivity          mass
#> 191                    resistivity                    resistivity          mass
#> 192                    resistivity                    resistivity        length
#> 193                    resistivity                    resistivity        length
#> 194                    resistivity                    resistivity        length
#> 195                    resistivity                    resistivity        length
#> 196                    resistivity                    resistivity          time
#> 197                    resistivity                    resistivity          time
#> 198                    resistivity                    resistivity          time
#> 199                    resistivity                    resistivity          time
#> 200                    resistivity                    resistivity       current
#> 201                    resistivity                    resistivity       current
#> 202                    resistivity                    resistivity       current
#> 203                    resistivity                    resistivity       current
#> 204                    conductance                    conductance          mass
#> 205                    conductance                    conductance          mass
#> 206                    conductance                    conductance          mass
#> 207                    conductance                    conductance          mass
#> 208                    conductance                    conductance        length
#> 209                    conductance                    conductance        length
#> 210                    conductance                    conductance        length
#> 211                    conductance                    conductance        length
#> 212                    conductance                    conductance          time
#> 213                    conductance                    conductance          time
#> 214                    conductance                    conductance          time
#> 215                    conductance                    conductance          time
#> 216                    conductance                    conductance       current
#> 217                    conductance                    conductance       current
#> 218                    conductance                    conductance       current
#> 219                    conductance                    conductance       current
#> 220                   magneticFlux                   magneticFlux          mass
#> 221                   magneticFlux                   magneticFlux          mass
#> 222                   magneticFlux                   magneticFlux          mass
#> 223                   magneticFlux                   magneticFlux          mass
#> 224                   magneticFlux                   magneticFlux        length
#> 225                   magneticFlux                   magneticFlux        length
#> 226                   magneticFlux                   magneticFlux        length
#> 227                   magneticFlux                   magneticFlux        length
#> 228                   magneticFlux                   magneticFlux          time
#> 229                   magneticFlux                   magneticFlux          time
#> 230                   magneticFlux                   magneticFlux          time
#> 231                   magneticFlux                   magneticFlux          time
#> 232                   magneticFlux                   magneticFlux       current
#> 233                   magneticFlux                   magneticFlux       current
#> 234                   magneticFlux                   magneticFlux       current
#> 235                   magneticFlux                   magneticFlux       current
#> 236            magneticFluxDensity            magneticFluxDensity          mass
#> 237            magneticFluxDensity            magneticFluxDensity          mass
#> 238            magneticFluxDensity            magneticFluxDensity          mass
#> 239            magneticFluxDensity            magneticFluxDensity          time
#> 240            magneticFluxDensity            magneticFluxDensity          time
#> 241            magneticFluxDensity            magneticFluxDensity          time
#> 242            magneticFluxDensity            magneticFluxDensity       current
#> 243            magneticFluxDensity            magneticFluxDensity       current
#> 244            magneticFluxDensity            magneticFluxDensity       current
#> 245                     inductance                     inductance          mass
#> 246                     inductance                     inductance          mass
#> 247                     inductance                     inductance          mass
#> 248                     inductance                     inductance          mass
#> 249                     inductance                     inductance        length
#> 250                     inductance                     inductance        length
#> 251                     inductance                     inductance        length
#> 252                     inductance                     inductance        length
#> 253                     inductance                     inductance          time
#> 254                     inductance                     inductance          time
#> 255                     inductance                     inductance          time
#> 256                     inductance                     inductance          time
#> 257                     inductance                     inductance       current
#> 258                     inductance                     inductance       current
#> 259                     inductance                     inductance       current
#> 260                     inductance                     inductance       current
#> 261                    illuminance                    illuminance    luminosity
#> 262                    illuminance                    illuminance    luminosity
#> 263                    illuminance                    illuminance        length
#> 264                    illuminance                    illuminance        length
#> 265                 specificEnergy                 specificEnergy          time
#> 266                 specificEnergy                 specificEnergy          time
#> 267                 specificEnergy                 specificEnergy        length
#> 268                 specificEnergy                 specificEnergy        length
#> 269                 doseEquivalent                 doseEquivalent          time
#> 270                 doseEquivalent                 doseEquivalent          time
#> 271                 doseEquivalent                 doseEquivalent        length
#> 272                 doseEquivalent                 doseEquivalent        length
#> 273              catalyticActivity              catalyticActivity          time
#> 274              catalyticActivity              catalyticActivity          time
#> 275              catalyticActivity              catalyticActivity        amount
#> 276              catalyticActivity              catalyticActivity        amount
#> 277                       pressure                       pressure          mass
#> 278                       pressure                       pressure          mass
#> 279                       pressure                       pressure          mass
#> 280                       pressure                       pressure          time
#> 281                       pressure                       pressure          time
#> 282                       pressure                       pressure          time
#> 283                       pressure                       pressure        length
#> 284                       pressure                       pressure        length
#> 285                       pressure                       pressure        length
#> 286                 transmissivity                 transmissivity        length
#> 287                 transmissivity                 transmissivity        length
#> 288                 transmissivity                 transmissivity          time
#> 289                 transmissivity                 transmissivity          time
#> 290             massSpecificLength             massSpecificLength        length
#> 291             massSpecificLength             massSpecificLength        length
#> 292             massSpecificLength             massSpecificLength          mass
#> 293             massSpecificLength             massSpecificLength          mass
#> 294              massSpecificCount              massSpecificCount dimensionless
#> 295              massSpecificCount              massSpecificCount dimensionless
#> 296              massSpecificCount              massSpecificCount          mass
#> 297              massSpecificCount              massSpecificCount          mass
#>     power
#> 1    <NA>
#> 2      -2
#> 3    <NA>
#> 4      -2
#> 5    <NA>
#> 6       1
#> 7    <NA>
#> 8       1
#> 9    <NA>
#> 10     -1
#> 11   <NA>
#> 12     -1
#> 13   <NA>
#> 14     -2
#> 15   <NA>
#> 16     -2
#> 17      3
#> 18     -2
#> 19      3
#> 20     -2
#> 21   <NA>
#> 22     -1
#> 23   <NA>
#> 24     -1
#> 25   <NA>
#> 26     -3
#> 27   <NA>
#> 28     -3
#> 29   <NA>
#> 30     -1
#> 31   <NA>
#> 32     -1
#> 33   <NA>
#> 34     -1
#> 35     -1
#> 36   <NA>
#> 37     -1
#> 38     -1
#> 39   <NA>
#> 40     -1
#> 41     -1
#> 42      3
#> 43     -3
#> 44      3
#> 45     -3
#> 46      3
#> 47     -1
#> 48      3
#> 49     -1
#> 50   <NA>
#> 51     -3
#> 52     -1
#> 53   <NA>
#> 54     -3
#> 55     -1
#> 56   <NA>
#> 57     -3
#> 58     -1
#> 59   <NA>
#> 60     -2
#> 61     -1
#> 62   <NA>
#> 63     -2
#> 64     -1
#> 65   <NA>
#> 66     -2
#> 67     -1
#> 68     -1
#> 69      3
#> 70     -1
#> 71      3
#> 72   <NA>
#> 73     -3
#> 74   <NA>
#> 75     -3
#> 76   <NA>
#> 77     -1
#> 78   <NA>
#> 79     -1
#> 80   <NA>
#> 81     -1
#> 82     -1
#> 83   <NA>
#> 84     -1
#> 85     -1
#> 86   <NA>
#> 87     -1
#> 88     -1
#> 89   <NA>
#> 90     -1
#> 91   <NA>
#> 92     -1
#> 93   <NA>
#> 94     -2
#> 95   <NA>
#> 96     -2
#> 97   <NA>
#> 98     -3
#> 99   <NA>
#> 100    -3
#> 101  <NA>
#> 102    -2
#> 103  <NA>
#> 104    -2
#> 105  <NA>
#> 106    -2
#> 107  <NA>
#> 108    -2
#> 109    -1
#> 110     2
#> 111    -1
#> 112     2
#> 113  <NA>
#> 114  <NA>
#> 115    -2
#> 116  <NA>
#> 117  <NA>
#> 118    -2
#> 119  <NA>
#> 120  <NA>
#> 121    -2
#> 122  <NA>
#> 123     2
#> 124    -2
#> 125  <NA>
#> 126     2
#> 127    -2
#> 128  <NA>
#> 129     2
#> 130    -2
#> 131  <NA>
#> 132     2
#> 133    -3
#> 134  <NA>
#> 135     2
#> 136    -3
#> 137  <NA>
#> 138     2
#> 139    -3
#> 140  <NA>
#> 141     2
#> 142    -3
#> 143    -1
#> 144  <NA>
#> 145     2
#> 146    -3
#> 147    -1
#> 148  <NA>
#> 149     2
#> 150    -3
#> 151    -1
#> 152  <NA>
#> 153     2
#> 154    -3
#> 155    -1
#> 156    -1
#> 157    -2
#> 158     4
#> 159     2
#> 160    -1
#> 161    -2
#> 162     4
#> 163     2
#> 164    -1
#> 165    -2
#> 166     4
#> 167     2
#> 168    -1
#> 169    -2
#> 170     4
#> 171     2
#> 172  <NA>
#> 173     2
#> 174    -3
#> 175    -2
#> 176  <NA>
#> 177     2
#> 178    -3
#> 179    -2
#> 180  <NA>
#> 181     2
#> 182    -3
#> 183    -2
#> 184  <NA>
#> 185     2
#> 186    -3
#> 187    -2
#> 188  <NA>
#> 189     3
#> 190    -3
#> 191    -2
#> 192  <NA>
#> 193     3
#> 194    -3
#> 195    -2
#> 196  <NA>
#> 197     3
#> 198    -3
#> 199    -2
#> 200  <NA>
#> 201     3
#> 202    -3
#> 203    -2
#> 204    -1
#> 205    -2
#> 206     3
#> 207     2
#> 208    -1
#> 209    -2
#> 210     3
#> 211     2
#> 212    -1
#> 213    -2
#> 214     3
#> 215     2
#> 216    -1
#> 217    -2
#> 218     3
#> 219     2
#> 220  <NA>
#> 221     2
#> 222    -2
#> 223    -1
#> 224  <NA>
#> 225     2
#> 226    -2
#> 227    -1
#> 228  <NA>
#> 229     2
#> 230    -2
#> 231    -1
#> 232  <NA>
#> 233     2
#> 234    -2
#> 235    -1
#> 236  <NA>
#> 237    -2
#> 238    -1
#> 239  <NA>
#> 240    -2
#> 241    -1
#> 242  <NA>
#> 243    -2
#> 244    -1
#> 245  <NA>
#> 246     2
#> 247    -2
#> 248    -2
#> 249  <NA>
#> 250     2
#> 251    -2
#> 252    -2
#> 253  <NA>
#> 254     2
#> 255    -2
#> 256    -2
#> 257  <NA>
#> 258     2
#> 259    -2
#> 260    -2
#> 261  <NA>
#> 262    -2
#> 263  <NA>
#> 264    -2
#> 265    -2
#> 266     2
#> 267    -2
#> 268     2
#> 269    -2
#> 270     2
#> 271    -2
#> 272     2
#> 273    -1
#> 274  <NA>
#> 275    -1
#> 276  <NA>
#> 277  <NA>
#> 278    -2
#> 279     1
#> 280  <NA>
#> 281    -2
#> 282     1
#> 283  <NA>
#> 284    -2
#> 285     1
#> 286     2
#> 287    -1
#> 288     2
#> 289    -1
#> 290  <NA>
#> 291    -1
#> 292  <NA>
#> 293    -1
#> 294  <NA>
#> 295    -1
#> 296  <NA>
#> 297    -1
#> 
# }
```
