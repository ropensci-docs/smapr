# Set credentials for NASA's Earthdata portal

To use smapr, users need to provide NASA Earthdata portal credentials.
This function allows users to interactively set these credentials via
the user's Earthdata username and password.

## Usage

``` r
set_smap_credentials(username, password, save = TRUE, overwrite = FALSE)
```

## Arguments

- username:

  A character string of your Earthdata portal username

- password:

  A character string of your Earthdata portal password

- save:

  Logical: whether to save your credentials to your .Renviron file
  (e.g., ~/.Renviron). Previous Earthdata credentials will not be
  overwritten unless `overwrite = TRUE`.

- overwrite:

  Logical: whether to overwrite previous Earthdata credentials in your
  .Renviron file (only applies when `save = TRUE`)

## Value

No return value, called for side effects (sets environment variables and
optionally saves credentials to .Renviron).

## Details

If you do not yet have a username and password, register for one here:
https://urs.earthdata.nasa.gov/

A warning: do not commit your username and password to a public
repository! This function is meant to be used interactively, and not
embedded within a script that you would share.

## Examples

``` r
if (FALSE) { # \dontrun{
set_smap_credentials('myusername', 'mypassword')
} # }
```
