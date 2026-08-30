# Get stats on users

Get stats on which users reported the most species or had the most
observations within a given range. This range can be by user, place,
project, day or date range. Output will be a count of the total number
of taxa observed at each taxonomic level.

## Usage

``` r
get_inat_user_stats(
  date = NULL,
  date_range = NULL,
  place = NULL,
  project = NULL,
  uid = NULL
)
```

## Arguments

- date:

  Retrieve observations on a specific date. Must be a string in the form
  "YYYY-MM-DD".

- date_range:

  A vector of dates defining a range, each in the form "YYYY-MM-DD".

- place:

  Get taxon stats by place. You can find place IDs on the [iNaturalist
  website](https://www.inaturalist.org/places). Must be a numeric ID.

- project:

  Get taxon stats by a project's numeric ID.

- uid:

  Get taxon stats by user ID (string).

## Value

A list containing two data.frames, with users sorted by either number of
observations or number of species observed.

## Examples

``` r
if (FALSE) { # \dontrun{
 counts <- get_inat_user_stats(date = "2010-06-14")
} # }
```
