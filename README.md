# Music Metadata Visualisation (WASABI dataset)

A visual study of a music metadata collection, preprocessed in R and presented through Tableau dashboards.

Coursework project, MSc Artificial Intelligence and Robotics.

## Data

The WASABI corpus of albums and artists, held as R data files covering roughly 3,000 artists. The fields kept for the analysis are the ones that carry something visual:

`name`, `country`, `language`, `genre`, `publicationDate`, `dateRelease`, `id_artist`, `title` and `deezerFans`

Country and language support maps, the two date fields support timelines, genre supports composition, and `deezerFans` gives a popularity measure to weight the rest against.

## Preprocessing in R

`My_Pre-Processing3.R` reads the `.rds` files, selects those fields, inspects types and counts missing values per column, and cleans the result into a flat table for Tableau. Written with `dplyr` and `readr`, with `ggplot2` and `plotly` used to check distributions before exporting, and `shiny` components explored for an interactive version.

## Dashboards

Three Tableau workbooks, each answering a different question:

```
Map.twb          where the music comes from, by country
gantt view.twb   how releases are distributed over time
pie chart.twb    how the catalogue breaks down by genre and language
```

## Files

```
My_Pre-Processing3.R              R preprocessing
albums_all_artists_3000.rds       album level data
wasabi_all_artists_3000.rds       artist level data
iadata.csv                        cleaned table exported for Tableau
Map.twb, gantt view.twb, pie chart.twb
project report.pdf                written report
final ppt.pptx                    presentation
```

## Running it

Open `My_Pre-Processing3.R` in RStudio and run it to regenerate `iadata.csv`, then open the `.twb` workbooks in Tableau Desktop or Tableau Public and point them at that file.

```r
install.packages(c("readr","dplyr","ggplot2","plotly","scales","ggthemes"))
```
