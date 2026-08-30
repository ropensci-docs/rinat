# Download observations for a user

Get all the observations of a specific iNaturalist user.

## Usage

``` r
get_inat_obs_user(username, maxresults = 100)
```

## Arguments

- username:

  username of the iNaturalist user to fetch records

- maxresults:

  the maximum number of results to return

## Value

a list with full details on a given record

## Examples

``` r
if (FALSE) { # \dontrun{
  m_obs <- get_inat_obs(query="Monarch Butterfly")
  get_inat_obs_user(as.character(m_obs$user_login[1]))
} # }
```
