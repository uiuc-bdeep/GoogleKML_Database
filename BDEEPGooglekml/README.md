# BDEEPGooglekml R package

## Installation
First, to install the package dependencies, execute the following in R terminal:
```
install.packages("devtools", dependencies=T)
install.packages("DBI")
install.packages("RPostgreSQL")
```

Finally, to install (only for the first time) or update the package, use:
```
devtools::install_github("uiuc-bdeep/GoogleKML_Database/BDEEPGooglekml")
```

In some cases, you might need to restart the server to get rid of all errors and warnings before loading the library. After this, use command to load the BDEEPZillow library.
```
library(BDEEPGooglekml)
```

## Content
The current available data & functions are as followed. All of them have been tested on infousa_2018 database. Function `get_cairo_usr` can also be used to get data from other databases (with great pain).

### Main functions
* [get_cairo_usr](./R/googlekml.R)

This function is similar to other `get_*_usr` functions available in other BDEEP R packages. For detailed examples, see the one in the BDEEPZillow package.

```
@description This function gets from database according to a user-specified query.
@param query         A string specifying the query sent to database
@param database_name A string indicating the database name
@param host_ip       A string indicating the ip address of the database VM
@examples # Select single field from a given table
@examples data <- get_from_db_usr("SELECT COUNT(*) FROM routes")
@return A data.frame returned by the given query.
```

* [db_type_converter](./R/converter.R)

To convert data types from database into desired types in R, one can modify this function for easier processing.
```
@description This function converts the type to align with the requirement. See requirement online.
@param data    The actual data.frame to convert.
@param dbname  The name of the database. Used to distinguish data.
@return The modified data.frame
```
