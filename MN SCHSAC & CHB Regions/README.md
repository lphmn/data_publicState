The CHB file has five metro cities that do not have a county assigned to them because I won't have access to this level of detail.
The metro cities start with _ so when they are assigned a primary key using rownumber, they are ordered last.

Huge shoutout to the ggplot2 developers for establishing county borders without the use of shape files. I was able to utilize plotly and build the MN_SCHSACRegion_CHB_County locations for MN CHB's and MH Schsac Regions. The most difficult and unique location is North County CHB because it consists of three counties that are not all connected (Beltrami county) is in between them which makes order the latitude and longitude not possible. So what I found is if I don't put a chb order for lake of the woods county (the county not attached to clearwater and hubbard) and also arrange by the order column, it will still build the map correctly. 
If using R, here are some simply scripts to create maps with ggplot2
# County
df_mnMap |> 
  dplyr::arrange(order) |> 
  ggplot(aes(x = long, y = lat, group= mapPrimaryKey,  fill= order)) +
  geom_polygon(color="black")
# Schsac Region
  df_mnMap |> 
  dplyr::arrange(schsacRegionOrder, order) |> 
  ggplot(aes(x = schsacRegionLong, y = schsacRegionLat, group= schsacRegionPK,  fill= schsacRegionOrder))+
  geom_polygon(color="black")
# CHB
  df_mnMap |> 
  dplyr::arrange(chbOrder, order) |> #The orer is required because of situations like North County CHB 
  ggplot(aes(x = chbLong, y = chbLat, group= chbPK,  fill= chbOrder))
  geom_polygon(color="black")
