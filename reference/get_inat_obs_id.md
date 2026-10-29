# Get information on a specific observation

Get information on a specific observation

## Usage

``` r
get_inat_obs_id(id)
```

## Arguments

- id:

  a single id for an iNaturalist observation record

## Value

a list with full details on a given record

## Examples

``` r
if (FALSE) { # \dontrun{
m_obs <- get_inat_obs(query="Monarch Butterfly")
get_inat_obs_id(m_obs$id[1])
} # }
```
