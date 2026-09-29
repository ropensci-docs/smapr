# Download SMAP data

This function downloads SMAP data in HDF5 format.

## Usage

``` r
download_smap(files, directory = NULL, overwrite = TRUE, verbose = TRUE)
```

## Arguments

- files:

  A `data.frame` produced by
  [`find_smap()`](https://docs.ropensci.org/smapr/reference/find_smap.md)
  that specifies data files to download.

- directory:

  A local directory path in which to save data, specified as a character
  string. If left as `NULL`, data are stored in a user's cache
  directory.

- overwrite:

  TRUE or FALSE: should existing data files be overwritten?

- verbose:

  TRUE or FALSE: should messages be printed to indicate that files are
  being downloaded?

## Value

Returns a `data.frame` that appends a column called `local_dir` to the
input data frame, which consists of a character vector specifying the
local directory containing the downloaded files.

## Details

This function requires a username and password from NASA's Earthdata
portal. If you have an Earthdata username and password, pass them in
using the
[`set_smap_credentials()`](https://docs.ropensci.org/smapr/reference/set_smap_credentials.md)
function.

If you do not yet have a username and password, register for one here:
<https://urs.earthdata.nasa.gov/>

## Examples

``` r
if (FALSE) { # \dontrun{
files <- find_smap(id = "SPL4SMGP", dates = "2015-03-31", version = 8)
# files[1, ] refers to the first available data file
downloads <- download_smap(files[1, ])
} # }
```
