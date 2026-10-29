# Download observations or info from a project

Retrieve observations from a particular iNaturalist project. This
function can be used to get either observations or information from a
project by project name or ID.

## Usage

``` r
get_inat_obs_project(grpid, type = c("observations", "info"), raw = FALSE)
```

## Arguments

- grpid:

  Name of the group as an iNaturalist slug or group ID.

- type:

  Character, either "observations" or "info". "observations" returns all
  observations, and "info" returns project details similar to what you
  can find on a project's page.

- raw:

  Logical. If TRUE and searching for project info, returns the raw
  output of parsed JSON for that project. Otherwise just some basic
  information is returned as a list.

## Details

An iNaturalist slug is usually the project name as a single string with
words separated by hyphens. For instance, the project "World Oceans Week
2022" has a slug of "world-oceans-week-2022", which you can find by
searching projects on iNaturalist and looking at the [project's page's
URL](https://www.inaturalist.org/projects/world-oceans-week-2022).

## Examples

``` r
if (FALSE) { # \dontrun{
 get_inat_obs_project(354, type = "observations")
 get_inat_obs_project("crows-in-vermont", type="info",raw=FALSE)
} # }
```
