# Public Data Sets Repository

This repository contains various public datasets related to Minnesota's public health and economic data.  
**For the link to open in a new tab please perform the following CTRL+click (on Windows and Linux) or CMD+click (on MacOS)**
* Just like everything on the internet, links can eventually become outdated or broken.
* My hope is that state departments in Minnesota will start storing data in a way that allows programs like R and Python to access the data directly.

## Datasets

**MN_DEED**
   - Description: This dataset contains data from the Minnesota Department of Employment and Economic Development (DEED).
   - Source: 

**MN_PHDAP**
   - Description: This dataset includes information from the Public Health Data Access Portal (PHDAP) in Minnesota.
   - Source: [MN Public Health Data Access Portal](https://data.web.health.state.mn.us/web/mndata)

**MN_StiHiv**
   - Description: This dataset contains data on sexually transmitted infections (STIs) and HIV in Minnesota **Data converted from the PDF Reports**.
   - Source: [MDH STI Stats](https://www.health.state.mn.us/diseases/stds/stats/index.html)
   - Source [MDH HIV Stats](https://www.health.state.mn.us/diseases/hiv/stats/index.html)

**MN_Regions**
   - Description: This dataset includes information about the State Community Health Services Advisory Committee (SCHSAC) and Community Health Board (CHB) regions in Minnesota.
   - Source: The heavy lifting for this data set was doen with R and the ggplot2::map_data function. For the SCHSAC and CHB borders, I did create these by deleting points and reordering the points.
     
## Usage

By having these data sets in a csv format, programs like R and Python are able to pull the data directly into their applications

