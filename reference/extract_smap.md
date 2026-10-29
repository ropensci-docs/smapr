# Extracts contents of SMAP data

Extracts datasets from SMAP data files.

## Usage

``` r
extract_smap(data, name)
```

## Arguments

- data:

  A data frame produced by
  [`download_smap()`](https://docs.ropensci.org/smapr/reference/download_smap.md)
  that specifies input files from which to extract data.

- name:

  The path in the HDF5 file pointing to data to extract.

## Value

Returns a SpatRaster object.

## Details

The arguments `group` and `dataset` must refer specifically the group
and name within group for the input file, such as can be obtained with
[`list_smap()`](https://docs.ropensci.org/smapr/reference/list_smap.md).
This function will extract that particular dataset, returning a Raster
object.

## Examples

``` r
if (FALSE) { # \dontrun{
files <- find_smap(id = "SPL4SMGP", dates = "2015-03-31", version = 8)
downloads <- download_smap(files[1, ])
sm_raster <- extract_smap(downloads, name = '/Geophysical_Data/sm_surface')
} # }
```
