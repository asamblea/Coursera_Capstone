# Introduction

International and domestic travel movements and oversea students are significantly disrupted due to the outbreak of COVID-19. In February 2020, overseas visitor arrivals to Australia decreased 26% compared to the same month a year ago.[[1\]](#_ftn1) 

Tourism and international students in Australia are an important component of the Australian economy. Tourism consists of domestic and international components and the contribution was a record $44.6 billion in 2019.[[2\]](#_ftn2) International education was worth $32.4 billion to the Australian economy in 2017–18.[[3\]](#_ftn3) 

The economy, international and domestic movements are expected to rebound as the pandemic finishes. This report explores the neighbourhoods in three popular Australian local government areas (LGA) and nine capital cities of selected countries and makes recommendations for tourists, international students and people who are going to move around in Australia. 

This report presents the similarity and dissimilarity among the twelve areas by analysing venues in neighbourhoods. Neighbourhoods are grouped into clusters based on venue categories by using K-means clustering algorithm.

In this report, only suburbs in LGAs in Australia, Shanghai and Beijing China will be presented, discussed as illustration.

# Data

1. LGAs in Australia

In 2019, New South Wales, Victoria and Queensland are the top 3 states in Australia for foreign enrolment and arrivals.[[4\]](#_ftn4) [[5\]](#_ftn5) 

Suburbs in the City of Sydney, the City of Melbourne and the City of Brisbane, as they have highest population density in New South Wales, Victoria and Queensland respectively.[[6\]](#_ftn6)

2. Source countries

China, India, Nepal, Vietnam and Malaysia are the top 5 countries and regions sending students to Australia.[[7\]](#_ftn7) China, New Zealand, USA, UK and Japan are the top 5 source countries of short-term visitor arrivals in Australia.[[8\]](#_ftn8)

Administration divisions are defined and named differently in these countries. In this analysis, administration division is named suburb for consistency and clarity. Suburbs in the capital cities of India, Nepal, Vietnam, Malaysia, UK and Japan are included in this analysis. 

Considering the close relationship between Australia and New Zealand, the large population in China, India and USA, the top two populous cities in each country are included in this analysis. These cities are Auckland City and Christchurch in New Zealand [[9\]](#_ftn9), Beijing and Shanghai in China[[10\]](#_ftn10), Delhi and Mumbai city in India[[11\]](#_ftn11) and New York City and Los Angeles in US[[12\]](#_ftn12).

# Methodology

1. Scrape and process data

In this analysis, suburb names are scraped from Wikipedia using Beautiful Soup Python Library. The latitude and longitude coordinates of suburbs are located using GeoPy.

![A screenshot of a cell phone  Description automatically generated](file:////Users/xiao/Library/Group%20Containers/UBF8T346G9.Office/TemporaryItems/msohtmlclip/clip_image001.png)

The data of the top 100 venues that are in each suburb within a radius of 500 meters are collected by using Foursquare API.

![A screenshot of a cell phone  Description automatically generated](file:////Users/xiao/Library/Group%20Containers/UBF8T346G9.Office/TemporaryItems/msohtmlclip/clip_image002.png)

There are 337 unique venue categories.

2. Analyse suburbs

Perform one hot encoding and prepare the dataset for ML algorithm

![A picture containing black, laptop, large, man  Description automatically generated](file:////Users/xiao/Library/Group%20Containers/UBF8T346G9.Office/TemporaryItems/msohtmlclip/clip_image003.png)

Group rows by suburb and by taking the mean of the frequency of occurrence of each category.

![A close up of a black keyboard  Description automatically generated](file:////Users/xiao/Library/Group%20Containers/UBF8T346G9.Office/TemporaryItems/msohtmlclip/clip_image004.png)

Get the top 10 most common venues in each suburb

![A screenshot of a cell phone  Description automatically generated](file:////Users/xiao/Library/Group%20Containers/UBF8T346G9.Office/TemporaryItems/msohtmlclip/clip_image005.png)

3.  Cluster suburbs

As venues in a suburb may belong to the same venue categories, k-means algorithm is used to cluster suburbs into 5 clusters. 

![A close up of a street  Description automatically generated](file:////Users/xiao/Library/Group%20Containers/UBF8T346G9.Office/TemporaryItems/msohtmlclip/clip_image006.png)

4. Data visualisation

Clusters are visualised on maps using Folium package

The City of Sydney and clusters

![A picture containing text, map  Description automatically generated](file:////Users/xiao/Library/Group%20Containers/UBF8T346G9.Office/TemporaryItems/msohtmlclip/clip_image007.png)

The City of Melbourne and clusters

![A picture containing text, map  Description automatically generated](file:////Users/xiao/Library/Group%20Containers/UBF8T346G9.Office/TemporaryItems/msohtmlclip/clip_image008.png)

The City of Brisbane and clusters

![A picture containing text, map  Description automatically generated](file:////Users/xiao/Library/Group%20Containers/UBF8T346G9.Office/TemporaryItems/msohtmlclip/clip_image009.png)

Shanghai, China and clusters

![img](file:////Users/xiao/Library/Group%20Containers/UBF8T346G9.Office/TemporaryItems/msohtmlclip/clip_image010.png)

Beijing, China and clusters

![A picture containing text, map  Description automatically generated](file:////Users/xiao/Library/Group%20Containers/UBF8T346G9.Office/TemporaryItems/msohtmlclip/clip_image011.png)

# Results

As shown in the maps, cluster 2 and 4 are the largest clusters. Another interesting result is that based on the 10 most common venue categories in each suburb, suburbs in Beijing and Shanghai are clustered into cluster 1, 2, 4 and suburbs in Sydney and Melbourne are clustered into cluster 2, 4.

![A close up of a sign  Description automatically generated](file:////Users/xiao/Library/Group%20Containers/UBF8T346G9.Office/TemporaryItems/msohtmlclip/clip_image012.png)

By examining each cluster, we can determine the discriminating venue categories that distinguish each cluster and identify the similarity between suburbs in regions.

Cluster 0 - Park

![A screenshot of text  Description automatically generated](file:////Users/xiao/Library/Group%20Containers/UBF8T346G9.Office/TemporaryItems/msohtmlclip/clip_image013.png)

Cluster 1 – Chinese restaurant 

![img](file:////Users/xiao/Library/Group%20Containers/UBF8T346G9.Office/TemporaryItems/msohtmlclip/clip_image014.png)

Cluster 2 – coffee shop

![A close up of a piece of paper  Description automatically generated](file:////Users/xiao/Library/Group%20Containers/UBF8T346G9.Office/TemporaryItems/msohtmlclip/clip_image015.png)

Cluster 3 – Bus station

![A screenshot of a cell phone  Description automatically generated](file:////Users/xiao/Library/Group%20Containers/UBF8T346G9.Office/TemporaryItems/msohtmlclip/clip_image016.png)

Cluster 4 - Balance

![A close up of a piece of paper  Description automatically generated](file:////Users/xiao/Library/Group%20Containers/UBF8T346G9.Office/TemporaryItems/msohtmlclip/clip_image017.png)

# Discussion

The City of Brisbane is divided into smaller suburbs and therefore parks and bus stations are stand out in some suburb. 

 

The cluster result will be more meaningful if the other 4 regions were divided into smaller segments. We will be able to take the insight of the area of culture centre, infrastructure and facilities, bus station, nature parks and etc in each region.

# Conclusion

According to available dataset, suburbs in the City of Sydney, the City of Melbourne, the City of Brisbane, Beijing and Shanghai can be clustered as park area, Chinese restaurant area, coffee shop area, bus station area and a balanced area.

There are more coffee shop areas in Australia while more Chinese restaurant area in China.

------

[[1\]](#_ftnref1)https://www.abs.gov.au/ausstats/abs@.nsf/Latestproducts/3401.0Media%20Release1Feb%202020?opendocument&tabname=Summary&prodno=3401.0&issue=Feb%202020&num=&view=

[[2\]](#_ftnref2) *Latest International Visitor Survey (Ivs) Results* Australian Trade and Investment Commission, Australian Government

[[3\]](#_ftnref3) *Overseas students in Australian higher education: a quick guide* Parliament of Australia 

[[4\]](#_ftnref4) *Overseas students in Australian higher education: a quick guide* Parliament of Australia 

[[5\]](#_ftnref5)https://www.abs.gov.au/ausstats/abs@.nsf/Latestproducts/3401.0Media%20Release1Feb%202020?opendocument&tabname=Summary&prodno=3401.0&issue=Feb%202020&num=&view=

[[6\]](#_ftnref6) The Australian Bureau of Statistics

[[7\]](#_ftnref7) *Overseas students in Australian higher education: a quick guide* Parliament of Australia 

[[8\]](#_ftnref8) https://www.abs.gov.au/ausstats/abs@.nsf/Latestproducts/3401.0Media%20Release1Feb%202020?opendocument&tabname=Summary&prodno=3401.0&issue=Feb%202020&num=&view=

[[9\]](#_ftnref9) Statistics New Zealand

[[10\]](#_ftnref10) http://www.stats.gov.cn/english/

[[11\]](#_ftnref11) <http://censusindia.gov.in/2011-prov-results/paper2/data_files/India2/1.%20Data%20Highlight.pdf>

[[12\]](#_ftnref12) *http://tourism-intelligence.com/Signatures/THE%20TOP%20TEN%20US%20STATES%20FOR%20OUTBOUND%20TRAVEL.pdf*