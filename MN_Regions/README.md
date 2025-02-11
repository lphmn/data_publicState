The LatLong_Mn.csv and LatLong_SchsacRegionChbCounty.csv files are used to create maps in R with GGPlot2.
  - The LatLong_MN file was created directly with the ggplot2::map_data function.
  - The LatLong_SchsacRegionChbCounty file was created with the
    - ggplot2::map_data function for the county attributes
    - I created the SCHSAC and CHB attributes
  
The SchsacRegionChbCounty.csv file is used as a central place for the geography breakdown. If the region/chb change, I just have to change it here.

Huge shoutout to the ggplot2 developers for establishing county borders without the use of shape files. I was able to utilize plotly and build the MN_SCHSACRegion_CHB_County locations for MN CHB's and MH Schsac Regions. The most difficult and unique location is North County CHB because it consists of three counties that are not all connected (Beltrami county) is in between them which makes order the latitude and longitude not possible. So what I found is if I don't put a chb order for lake of the woods county (the county not attached to clearwater and hubbard) and also arrange by the order column, it will still build the map correctly. 
If using R, here are some simply scripts to create maps with ggplot2

library(ggplot2)

df_latLongMn <- read.csv("https://raw.githubusercontent.com/quincountychsmn/MN_PublicData/main/MN_Regions/LatLong_Mn.csv")
df_latLongSchsacRegionChbCounty <- read.csv("https://raw.githubusercontent.com/quincountychsmn/MN_PublicData/main/MN_Regions/LatLong_SchsacRegionChbCounty.csv")


#State
df_latLongMn |>
  dplyr::arrange(mnOrder) |>
  ggplot(aes(x = mnLong, y = mnLat, group= mnMapPK, fill= mnOrder))+
  geom_polygon(color="black")

#SCHSAC
df_latLongSchsacRegionChbCounty |>
  dplyr::arrange(schsacRegionOrder, countyOrder) |>
  ggplot(aes(x = schsacRegionLong, y = schsacRegionLat, group= schsacRegionMapPK, fill= schsacRegionOrder))+
  geom_polygon(color="black")

#CHB
df_latLongSchsacRegionChbCounty |>
  dplyr::arrange(chbOrder, countyOrder) |>
  ggplot(aes(x = chbLong, y = chbLat, group= chbMapPK, fill= chbOrder)) + 
  geom_polygon(color="black")

#County
df_latLongSchsacRegionChbCounty |>
  dplyr::arrange(countyOrder) |>
  ggplot(aes(x = countyLong, y = countyLat, group= countyFips, fill= countyOrder)) +
  geom_polygon(color="black")
