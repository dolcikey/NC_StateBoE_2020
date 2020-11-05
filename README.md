
## 2020 Election: North Caroline Early Voting and Absentee Data

In preparation for tomorrow, Election Day in the United States, I took the time to learn how to build a dashboard in Tableau. Having only used Seaborn/Matplotlib libraries for my previous data analyses, I thought the best way to learn was to jump in the deep end.

### Why North Carolina? 
North Carolina is a swing state, and in addition to the Presidential election, has competitive House races in their 8th, 9th, and 11th congressional districts, where once safe House Republicans find themselves suddenly in competitive races following the redistricting of Congressional Districts in 2019.

Additionally, North Carolina is one of the most transparent states when it comes to public election data with multiple CSV files available with both county and congressional districts (the hardest data to find as they are subject to change with redistricting which often contain split counties).

## Data Cleaning
Taking the 2.16 GB final data file, I imported it in a Jupyter notebook. I dropped the additional columns that I did not need for brevity and to make it easier to work with. To join it to my shapefile, I editied for format of the county to title. 

I added a Voted column for all ACCEPTED and ACCEPTED - CURED votes. 

For party, I added a party column that listed Green Party (GRE), Libertarian (LIB), and Consitututional Party (CST) as OTHER. They accounted for a very small persentage of votes. Secondly, I kept Republican (REP), Democrat (DEM), and Unaffliated voters (UNA) separately. These were the Party IDs we are more interested in. 

<img src="/PNG/2020_North_Carolina_Votes_Nov_03.png">

## Tableau Dashboard
In Tableau, I joined the US Shapefile and the data by county name for North Carolina. 

Map

For the map I used the geomety in the shape file to create a map of North Carolina, added by county, and then added parties to the tool tips by way of calculated fields to show numbers of votes by party ID. The map itself showed by color where the votes were heaviest, and these did tend to be in areas where Democrats voted most heavily. 

State Wide

I charted a bar chart for the statewide vote which showed the majority of received votes were Democrat with many also Unaffiliated voters which according to additional polls and speculations are that those are likely majority Biden voters, but has yet to be seen. 

Congressional Districs

This is the most dificult data usually to get as Congressional Districts change, zipcodes are not always included in voter data, and NC had underwent redistricting in 2019. Fortunately after looking through more data, I was happy to report that in one of the files, NC did include a column for congressional districts and created a bar chart for these by Party ID separated by congressional districts. This is important as there are competitive races for the House in districs 8, 9, and 11 this year. 



### Interactive Tableau Dashboard
https://public.tableau.com/profile/dolcikey#!/vizhome/NorthCarolinaAbsenteeBallotCount/NorthCarolinaPresidentalElectionVotes?publish=yes

### Data Source
https://dl.ncsbe.gov/?prefix=ENRS/2020_11_03/
