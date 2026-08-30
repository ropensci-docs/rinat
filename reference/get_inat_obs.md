# Download iNaturalist data

Primary function to retrieve observations from iNaturalist, allows users
to search for data, or just filter results by a subset of what is
offered by the API.

## Usage

``` r
get_inat_obs(
  query = NULL,
  taxon_name = NULL,
  taxon_id = NULL,
  place_id = NULL,
  quality = NULL,
  geo = NULL,
  annotation = NULL,
  year = NULL,
  month = NULL,
  day = NULL,
  bounds = NULL,
  photo_license = NULL,
  maxresults = 100,
  meta = FALSE
)
```

## Arguments

- query:

  Query string for a general search.

- taxon_name:

  Filter by iNat taxon name. Note that this will also select
  observations of descendant taxa. Note that names are not unique, so if
  the name matches multiple taxa, no observations may be returned.

- taxon_id:

  Filter by iNat taxon ID. Note that this will also select observations
  of descendant taxa.

- place_id:

  Filter by iNat place ID.

- quality:

  The quality grade to be used. Must be either "casual" or "research".
  If left blank both will be returned.

- geo:

  Flag for returning only results that are georeferenced, TRUE will
  exclude non-georeferenced results, but they cannot be excluded.

- annotation:

  Filter by annotation. Vector of length 2, the first element being the
  term ID (e.g. "1" for life stage) and the second element being the
  value ID (e.g. "2" for adult). Refer to the [annotation
  documentation](https://forum.inaturalist.org/t/how-to-use-inaturalists-search-urls-wiki-part-2-of-2/18792#heading--annotations)
  to know which values to use.

- year:

  Return observations only in that year (can only be one year, not a
  range of years).

- month:

  Return observations only by month, must be numeric, 1...12

- day:

  Return observations only on a given day of the month, 1...31

- bounds:

  A bounding box of longitude (-180 to 180) and latitude (-90 to 90) to
  search within. It is a vector in the form of southern latitude,
  western longitude, northern latitude, and eastern longitude.
  Alternatively supply an sf or sp object from which the bounding box
  will be derived.

- photo_license:

  Filter by photo license. Values can be CC variations ("CC0", "CC-BY",
  CC-BY-NC", "CC-BY-SA", "CC-BY-ND", "CC-BY-NC-SA", "CC-BY-NC-ND"),
  "any" (any CC licence), or "none" (all rights reserved). Note that an
  observation and its photos don't necessarily have the same licence.

- maxresults:

  The maximum number of results to return. Should not be a number higher
  than 10000.

- meta:

  (logical) If TRUE, the output of this function is a list with metadata
  on the output and a data.frame of the data. If FALSE (default), just
  the data.frame.

## Value

A dataframe of the number of observations requested.

## Note

Filtering doesn't always work with the query parameter for some reason
(a problem on the API end). If you want to filter by time, it's best to
use the scientific name and put it in the 'taxa' field, and not in the
query field. Another issue is that the query parameter will search the
entire entry, so it is possible to get unintended results. Depending on
your use case it may be advisable to use the "taxon" field instead of
the query field.

## Examples

``` r
if (FALSE) { # \dontrun{
## Make a standard query
get_inat_obs(query = "Monarch Butterfly")

## Restrict to juveniles thanks to annotations
get_inat_obs(query = "possum", annotation = c(1, 8))

## Filter by a bounding box of Northern California
bounds <- c(38.44047, -125, 40.86652, -121.837)
get_inat_obs(query = "Mule Deer", bounds = bounds)

## Filter by taxon, allows higher order filtering,
## Here we can search for just stone flies (order Plecoptera)
get_inat_obs(taxon_name = "Plecoptera")

## Get metadata (the number of results found on the server)
out <- get_inat_obs(query = "Monarch Butterfly", meta = TRUE)
out$meta
} # }
```
