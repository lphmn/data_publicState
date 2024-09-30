# Public Data Sets Repository

This repository contains various public datasets related to Minnesota's public health and economic data. Below is a list of the datasets included:

## Datasets

**MN_DEED**
   - Description: This dataset contains data from the Minnesota Department of Employment and Economic Development (DEED).
   - Source: 

**MN_PHDAP**
   - Description: This dataset includes information from the Public Health Data Access Portal (PHDAP) in Minnesota.
   - Source: [https://data.web.health.state.mn.us/web/mndata]

**MN_StiHiv**
   - Description: This dataset contains data on sexually transmitted infections (STIs) and HIV in Minnesota **Data converted from the PDF Reports**.
   - Source: [https://www.health.state.mn.us/diseases/stds/stats/index.html] [https://www.health.state.mn.us/diseases/hiv/stats/index.html]

**MN_Regions**
   - Description: This dataset includes information about the State Community Health Services Advisory Committee (SCHSAC) and Community Health Board (CHB) regions in Minnesota.
   - Source: The heavy lifting for this data set was doen with R and the ggplot2::map_data function. For the SCHSAC and CHB borders, I did create these by deleting points and reordering the points.
     
## Usage

By having these data sets in a csv format, programs like R and Python are able to pull the data directly into their applications

