# Data and approach to use

To solve this problem, I need to take it step by step:
1.	Firstly, I need to get a list of suburbs, equivalent to neighborhoods, in order to be able to get the places for each one of them. In order to do this, I intend to use the webpage https://www.citypostcodes.com.au/Melbourne. A part of the transformation and cleansing I need to remove the ‘Postcode’ keyword after each suburb.
2.	I need to use Foursquare to explore the Greater Melbourne area and obtain places filtered by categories related to restaurants and coffee places.
3.	It will be necessary to not only extract usual attributes such as place name, latitude and longitude, category, but also rating and price tier. 
4.	In the labs we saw how to treat the place category with one hot encoding. We need to apply this treatment to two non-numeric features. Rating is numeric but it will need to be scaled in a range from 0 to 1. The following attributes will be transformed:
    1. place category: one hot encoding
    2. price tier: one hot encoding
    3. rating: scaling
5.	Group rows by suburb (equivalent to neighborhood) by taking the mean of the frequency of occurrence of each one-hot-encoded attribute.
6.	Use *k-means* to cluster the suburbs, initially into 4 clusters.
    1.	Increase the number of clusters.
    2.	Re-run *k-means* algorithm to get new groupings.
    3.	Repeat *i* and *ii* until satisfied with grouping, or until 10 clusters.
7.	Analyze which of the previous runs closely groups by rating and price tier and pick that run.
8.	Rank the clusters by number of places, average rating and average price tier.
9.	Visualize the results to spot what clusters, as identified by previous step, are not being served by as many cafes and restaurants as the rest of clusters. Also need to validate that the selected spot(s) is/are not in a poorly populated neighborhood (quite unlike in a major city)
