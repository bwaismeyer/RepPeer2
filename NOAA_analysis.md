# Using the NOAA Storm Database to Explore the Impact of Weather Events on US Public Health and Economy
Brian Waismeyer  
Thursday, April 23, 2015  

**NOTES**
-   can have sections beyond those included below
-   no more than 10 sentences in the synopsis
-   need to have at least one figure with a plot
-   no more than three figures total
-   show ALL code

## Synopsis
This is an exploratory analysis of an open database provided by the the U.S. 
National Oceanic and Atmospheric Administration (NOAA). It was guided by and
completed to fulfill requirements of a course on 
[Reproducible Research](https://www.coursera.org/course/repdata) on Coursera 
(April 6, 2015 session).

The database used contains data about storms in the United States along with
key estimates of how these storms impacted the human environment. More 
information about the database can be found 
[here](https://d396qusza40orc.cloudfront.net/repdata%2Fpeer2_doc%2Fpd01016005curr.pdf).

The analysis aimed to address two proposed questions:
1.  What types of storm events are most harmful to US population health?
2.  What types of events have the most impact on US economy?

**PROVIDE BRIEF SUMMARY WHEN ANALYSIS IS COMPLETE**

## Loading Supporting Resources

```r
library(ggplot2)    # for making our data visualizations
```

## Data Processing
The dataset for the analysis was provided by Coursera instructors but appeared
to be a faithful copy (or at least subset) of the original NOAA database. For
the purposes of the analysis, no "preprocessing" was assumed except that
conducted during measurement, collection, and database construction.

### Getting the Data

```r
# we quickly verify that we are not overwriting any local files...
if(file.exists("./NOAA_database.csv")) {
    # warn the user if a copy already exists
    stop("Please remove the 'NOAA_database.csv' file from the local working
         directory or - if the file is current - skip this processing step.")
} else {
    # if all is clear, we download the dataset
    download_url <- paste0("http://d396qusza40orc.cloudfront.net/",
                           "repdata%2Fdata%2FStormData.csv.bz2")
    
    download.file(url = download_url,
                  destfile = "./NOAA_database.csv")
    
    # clean up the url from the workspace
    rm(download_url)
}

# read the data into R
storms <- read.csv("./NOAA_database.csv")

# clean up the download file
unlink("./NOAA_database.csv")
```
### Reviewing the Data

## Results

