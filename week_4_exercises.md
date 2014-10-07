# Week 4 Exercises

## Before you start

Decide where you are going to store your work, i.e., any data sets that you download and modify, any scripts you might write or use, any other outputs that you create from the data. Options (not mutually exclusive) include:

* a standard folder on local storage on your laptop
* in the cloud; e.g. Dropbox or Google Drive folder
* in a versioned repository, such as git + GitHub

Name your work folders clearly and create subfolders if necessary. Do you care if you lose the folder?


## Finding Data

Data stores to use:

* City of Edinburgh Council (CEC) [Open Data Store](http://www.edinburghopendata.info/dataset)
* CEC [GitHub repository](https://github.com/edinburghcouncil/datasets)

And

* [Scottish Neighbourhood Statistics](http://www.sns.gov.uk/default.aspx)

### Tasks

Try to use data from the CEC data sets to answer the following questions **about Inverleith**:

1. How many allotments are there?
2. How many leisure centres are there?
3. How many museums and art galleries?
4. How many public bike parking facilities?




## Organising Tabular Data

1. Download CE

```
cat IN0730.csv IN0745.csv > 30mins.csv
```

Delete rows 1-4

Delete columns L-BJ

Delete rows 43-90

Delete rows 85-120

Delete all columns apart from pedal cycles and cars

2013-12-1 7:30:00

Connect apps to Drive
Fusion Tables

Survey information sheet
Duplicate
Delete rows 1-4, 40-62, blank rows
Delete columns A-B, C-H

Create new column C and copy all of column B to C

**Find**: ` / [0-9]+`

**Replace**: `  ` 

Search using regular expressions

Specific range: `'Survey Information'!B:B

**Find**: `[0-9]+ / `

**Replace**: `  ` 

Search using regular expressions

Specific range: `'Survey Information'!C:C

http://www.gridreferencefinder.com/batchConvert/batchConvert.php

