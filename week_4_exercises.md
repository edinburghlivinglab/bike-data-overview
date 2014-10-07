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

And possibly

* [Scottish Neighbourhood Statistics](http://www.sns.gov.uk/default.aspx)

### Tasks

Try to use data from the **CEC data sets** to answer the following questions **about Inverleith**. 

1. How many allotments are there?
2. How many leisure centres are there?
3. How many museums and art galleries?
4. How many public bike parking facilities?
5. Find out something interesting about Inverleith not already on this list.

You may be able to do this by identifying relevant data sets in the CEC data stores and just looking at the data.

You may find that some of the data is geocoded using [WGS84 latitude and longitude](http://en.wikipedia.org/wiki/World_Geodetic_System) coordinates; e.g., `55.954419, -3.1735552`. If you just paste these coordinates into a Google search bar, it will return a little map of the location.



## Organising Tabular Data

### First steps

1. Download the `Cepats 2013.xls` file from [CEPATS data](https://github.com/edinburghlivinglab/cyclehack/tree/master/CEPATS)
2. Import the file into Google Sheets (or use Libre Office or Excel). Create a new spreadsheet, then do `File > Import > Replace spreadsheet`.
3. Make a copy of the file and rename it, just in case you want to rewind to the original version at some point.
3. We are going to work with only two sheets: `IN0730` and `Survey Information`. Let's start with `IN0730`

### Working on `IN0730`

1. First, get clear all formatting.
2. Next, get rid of all rows except the header rows (i.e., containing the column labels) and the ones starting with 'Abbeyhill' and ending with 'Wester Coates Walkway'.
3. Get rid of all the columns except:
	4. the one with street names
	1. the one headed 'PEDAL CYCLES' 
	1. the one headed 'CARS & TAXIS'
4. There are currently two header rows; collapse these into one

### Working on `Survey Information`

1. Delete all rows apart from the ones with street locations; i.e. 5-43.
2. Delete all columns apart from the street location one and the one labeled 'O.S. GRID REF.'
3. Duplicate the 'O.S. GRID REF.' column; e.g. create new column C and copy all of column B to C.

#### Converting OS Grid Ref to LatLong

We want to just keep information to the left of the ` / ` in column B and just information to the right of the ` / ` in column C. 

Your goal is to end up with a sheet that looks like this:

![Locations XY](images/survey_xy.png =500x)

This will allow us to input our Grid Reference XY data into an application that convers the geocoordinates to WGS84 coordinates, which are more widely supported by by mapping coordinates.

We'll use `Edit > Find and replace` on each column separately, and we'll use regular expressions. These are the settings you should use in Google Sheets:

###### Column A

**Find**: ` / [0-9]+`

**Replace**: [leave blank]

Check the option: `Search using regular expressions`

Select `Specific range` and give it the value `'Survey Information'!B:B`

---
*NB The **replace** string should be empty. Also note that we are deliberately getting rid of the space following the `/` character. Similarly for the following replacement.*

---

###### Column B

**Find**: `[0-9]+ / `

**Replace**: [leave blank]

Check the option: `Search using regular expressions`

Select `Specific range` and give it the value `'Survey Information'!C:C`



#### Looking up LatLong

We are now going to use the [GridReferenceFinder](http://www.gridreferencefinder.com/batchConvert/batchConvert.php). This requires that you paste your tabular data into a box and tick some options. It should look like this:

![GridReferenceFinder](images/batchConvert.png =500x)

Paste the results back into a new sheet.

Next, you are are going to add the new data you've just created into `IN0730`. You want to add this new data as extra columns. The locations in `IN0730` should align with the street locations that you have just pasted in.

It should look something like this: 

![](images/15mins_geocoded.tiff =500x) 

You can now go ahead and delete the column with locations that pasted in, leaving just the new geo-coordinates. Give labels to these two new columns: `Latitude` and `Longitude`. Congratulations if you've reached this point successfully!



## Putting the data on a map

In this section of the exercise, you are going to take a few more steps that will allow you to do a simple visualisation of the data on a map. 

### Reorganising the data

We want to change the spreadsheet so tha


Select column D 1:38

Data > Sort range from D1 to D38

sort by Column D A->Z

https://support.google.com/fusiontables/answer/2476954?hl=en&topic=2569513&ctx=topic

https://www.google.com/fusiontables/data?docid=1BDnT5U1Spyaes0Nj3DXciJKa_tuu7CzNRXWdVA#map:id=3

[Fusion Tables](https://support.google.com/fusiontables/answer/2571232?hl=en)

Change feature styles > Map marker icons > Column > Use icon specified in a column > Select > Icon

Filter > Catagory 
choose either `cars` or `pedal cycles`