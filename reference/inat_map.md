# Plot iNaturalist observations

Plot observations from iNaturalist. You have the option of automatically
plotting, or returning a ggplot map object that you can add layers onto.

## Usage

``` r
inat_map(data, map = "usa", subregion = ".", plot = TRUE)
```

## Arguments

- data:

  data frame of iNaturalist observations.

- map:

  the map area to plot, default is USA. See the same `map` argument in
  [`map_data`](https://ggplot2.tidyverse.org/reference/map_data.html)
  for available areas.

- subregion:

  the name of the subregion to plot. See the `region` argument in
  [`map_data`](https://ggplot2.tidyverse.org/reference/map_data.html)
  for more details.

- plot:

  a logical value. TRUE plots the map object and returns it, and FALSE
  returns a ggplot object that you can modify and plot later.

## Value

A ggplot map object.

## Examples

``` r
if (FALSE) { # \dontrun{
m_obs <- get_inat_obs(taxon_name = "Ambystoma maculatum")
salamander_map <- inat_map(m_obs, plot = FALSE)
### Now we can modify the returned map
salamander_map + borders("state") + theme_bw()
} # }
```
