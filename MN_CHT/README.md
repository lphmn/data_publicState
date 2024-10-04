CHT stands for County Health Table
The Minnesota Department of Health is the primary data steward for the County Health PDF Tables. For more information about the tables please visit https://www.health.state.mn.us/data/mchs/genstats/countytables/index.html#:~:text=The%20county%20health%20tables%20are%20a%20compilation%20of%20public%20health

The reason for moving the data to this GitHub repository is the data cannot be easily pulled into a shinyLive R application (an application ran without a server).  

The strength for saving the data in a friendly format does have a limitation. As I am not the data steward, I will need to ensure that any updates or edits to the data are reflected here. I will do my best to keep this information current, but I cannot guarantee that I will be able to maintain it consistently in the future.

**My wishlist is that MN data stewards begin storing their publicly available data in a friendlier manner.**

Notes:  
  * The reason only the counties and the state of MN have the location fips codes is for my process, I plan to recreate the rates in more of a dyncamic process.
    * However, by having the rates stored, I can check my work to prevent the spread of misinformation.
  * Some data won't exactly match what the PDF tables have. I worked with the great staff at MDH and they shared some updated data with me.
    * I did not update all the data in this repository because most of errors I found to be minor (difference of 1 count for counts greater than 20 plus).
    * However, I am a firm believer you should trust but always verify so if there is data in this repository that does not match the PDF table, please reach out to MDH for the most up to date data.
  * Some fields that seem to be incorrect in the PDF tables include
    * 2020 percent_birthOnMedicaid
    * 2017 and 2018 PNC attributes for the state of MN (MDH is working on a communication for this)   
