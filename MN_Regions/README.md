The LatLong_Mn.csv and LatLong_SchsacRegionChbCounty.csv files are used to create maps in R with GGPlot2.
  - The LatLong_MN file was created directly with the ggplot2::map_data function.
  - The LatLong_SchsacRegionChbCounty file was created with the
    - ggplot2::map_data function for the county attributes
    - I created the SCHSAC and CHB attributes
  
The SchsacRegionChbCounty.csv file is used as a central place for the geography breakdown. If the region/chb change, I just have to change it here.

Huge shoutout to the ggplot2 developers for establishing county borders without the use of shape files. I was able to utilize plotly and build the MN_SCHSACRegion_CHB_County locations for MN CHB's and MH Schsac Regions. The most difficult and unique location is North County CHB because it consists of three counties that are not all connected (Beltrami county) is in between them which makes order the latitude and longitude not possible. So what I found is if I don't put a chb order for lake of the woods county (the county not attached to clearwater and hubbard) and also arrange by the order column, it will still build the map correctly. 
If using R, here are some simply scripts to create maps with ggplot2
# County
df_mnMap |>  
  dplyr::arrange(order) |>  
  ggplot(aes(x = countyLong, y = countyLat, group= countyPK,  fill= countyOrder)) +  
  geom_polygon(color="black")
# Schsac Region
  df_mnMap |>  
  dplyr::arrange(schsacRegionOrder, order) |>  
  ggplot(aes(x = schsacRegionLong, y = schsacRegionLat, group= schsacRegionPK,  fill= schsacRegionOrder))+  
  geom_polygon(color="black")
# CHB
  df_mnMap |>  
  dplyr::arrange(chbOrder, order) |>   
  ggplot(aes(x = chbLong, y = chbLat, group= chbPK,  fill= chbOrder))  
  geom_polygon(color="black")


