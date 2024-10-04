CHT stands for County Health Table
The Minnesota Department of Health is the primary data steward for the County Health PDF Tables. For more information about the tables please visit [County Health Tables](https://www.health.state.mn.us/data/mchs/genstats/countytables/index.html#:~:text=The%20county%20health%20tables%20are%20a%20compilation%20of%20public%20health)

The reason for moving the data to this GitHub repository is the data cannot be easily pulled into a shinyLive R application (an application ran without a server).  

The strength for saving the data in a friendly format does have a limitation. As I am not the data steward, I will need to ensure that any updates or edits to the data are reflected here. I will do my best to keep this information current, but I cannot guarantee that I will be able to maintain it consistently in the future.

**My wishlist is that MN data stewards begin storing their publicly available data in a friendlier manner.**

Notes:  
  * The reason for having only location fips codes for counties and the state of Minnesota is the process that I am going to try to create is to calculate the rates in a more dynamic and adaptable manner.
    * However, by having the rates stored in this repository, I can check my work to reduce the spread of misinformation.
  * Some data won't precisely match the PDF tables. The fantastic team at MDH provided me with updated data.
    * I didn't update all the data in this repository since most of the errors were minor in my opinion, such as a difference of just one count for numbers greater than 20."
    * I firmly believe in 'trust but verify.' If you find data in this repository that doesn't match the PDF table, please contact MDH for the most up-to-date information.
  * Some fields that appear to be incorrect in the County Health PDF Tables include
    * 2020 percent_birthOnMedicaid
    * 2017 and 2018 PNC attributes for the state of MN (MDH is working on a communication for this)   
