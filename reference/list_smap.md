# Lists the contents of SMAP data files

This function returns a list of the contents of SMAP data files.

## Usage

``` r
list_smap(files, all = TRUE)
```

## Arguments

- files:

  A `data.frame` produced by
  [`download_smap()`](https://docs.ropensci.org/smapr/reference/download_smap.md)
  that specifies input data files.

- all:

  If TRUE a longer, more detailed list of information on each entry is
  provided.

## Value

Returns a list of `data.frame` objects that list the contents of each
data file in `files`.

## Examples

``` r
if (FALSE) { # \dontrun{
files <- find_smap(id = "SPL4SMGP", dates = "2015-03-31", version = 8)
files <- download_smap(files[1, ])
list_smap(files)
list_smap(files, all = TRUE)
} # }
```
