# Find SMAP data

This function searches for SMAP data on a specific date, returning a
`data.frame` describing available data.

## Usage

``` r
find_smap(id, dates, version)
```

## Arguments

- id:

  A character string that refers to a specific SMAP dataset, e.g.,
  `"SPL4SMGP"` for SMAP L4 Global 3-hourly 9 km Surface and Rootzone
  Soil Moisture Geophysical Data. See "Details" for a list of supported
  data types and their associated id codes.

- dates:

  An object of class Date or a character string formatted as To search
  for one specific date, this can be a Date object of length one. To
  search over a time interval, it can be a multi-element object of class
  Date such as produced by `seq.Date`.

- version:

  Which data version would you like to search for? Version information
  for each data product can be found at
  <https://nsidc.org/data/smap/version-history>

## Value

A data.frame with the names of the data files, the remote directory, and
the date.

## Details

There are many SMAP data products that can be accessed with this
function. Currently, smapr supports level 3 and level 4 data products,
each of which has an associated Data Set ID which is specified by the
`id` argument, described at <https://nsidc.org/data/smap/data> and
summarized below:

- SPL2SMAP_S:

  SMAP/Sentinel-1 Radiometer/Radar Soil Moisture

- SPL3FTA:

  Radar Northern Hemisphere Daily Freeze/Thaw State

- SPL3SMA:

  Radar Global Daily Soil Moisture

- SPL3SMP:

  Radiometer Global Soil Moisture

- SPL3SMAP:

  Radar/Radiometer Global Soil Moisture

- SPL4SMAU:

  Surface/Rootzone Soil Moisture Analysis Update

- SPL4SMGP:

  Surface/Rootzone Soil Moisture Geophysical Data

- SPL4SMLM:

  Surface/Rootzone Soil Moisture Land Model Constants

- SPL4CMDL:

  Carbon Net Ecosystem Exchange

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
# looking for data on one day:
find_smap(id = "SPL4SMGP", dates = "2015-03-31", version = 8)

# searching across a date range
start_date <- as.Date("2015-03-31")
end_date <- as.Date("2015-04-02")
date_sequence <- seq(start_date, end_date, by = 1)
find_smap(id = "SPL4SMGP", dates = date_sequence, version = 8)
} # }
```
