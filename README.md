# Airbnb Automated Classification System 

###By Jonathan Pichot, Fernando Melchor, and Avikal Somvanshi

#####Abstract—Machine Learning techniques from all ranges of complexity are used to analyze datasets. Unsupervised classification could be used to enhanced our understanding of a system by analyzing the classification outcome. While humans are good at classifying things visually, when multi-dimensionality is involved, machine learning can help us to close this gap and enhance our understanding. This project applies an unsupervised classification technique to Airbnb listings in New York City with the purpose of developing an automated categorization and rating system for listings to be used by consumers and Airbnb itself.

<img src="/paper/img/alllistings.png" width="808">



####Introduction
This project will explore the possibility of creating a machine-learning driven categorization system of Airbnb listings in New York City. A rating system similar to those a guidebook might provide, giving a tourist an idea of what kind of amenities are found around the listing. This project will focus on a combination of neighborhood attributes in the vicinity of the listing and some attributes on the listing itself. The classification system developed could be useful to tourists and Airbnb alike. Using the system, Airbnb customers in New York City would get a better idea of the amenities available in the neighborhood around their rental, and Airbnb could use the analysis to better understand their listing inventory and customer preferences. Is there stronger demand for cheaper listings? For listings with better public transit
connectivity? For listings close to certain kinds of amenities? There are several rich possible applications.

####Data & Methods
#####A. Airbnb Listings
The Airbnb listings for New York City were collected from InsideAirbnb.com,[2] a website run by a New York City-based housing activist named Murray Cox. The website scrapes Airbnb’s website for many cities around the world, creating snapshots of all listings on the site in a city on a given day. The data used in this analysis was from the scrape of New York City on March 2nd, 2017.

#####B. Outliers
To make sure the analysis was performed on Airbnb listings that are actually being rented we removed certain outliers. This left us with the listings with the below attributes:
*	Minimum of 7 or less nights per booking
*	Listing price of $500 or less
*	At least 1 review

#####C. Custom Attributes
In addition to the attributes collected by Inside Airbnb, we added four custom attributes to each listing. We developed using publicly available data. They are:
*	Median Household Income 
*	Craft Beer Count
*	Specialty Coffee Count
*	Connectivity Score

You can read more about how these custom attributes were built from different sources of data and geo-spatial operations at the Paper <Airbnb_Paper.pdf> and at the Jupyter Notebooks.
> 
<img src="/paper/img/workflow.png" width="808">
>

#### Clusters & Listing Profiles
#####1) Normal People: 
The Normal People cluster represents 55% of listings and has the lowest of all indicators, with a median income of $25,556 and an average price of $99 per night. It also has the lowest of our three custom indicators: coffee count, beer count, and connectivity score. As is clear on the map, the Normal People are clustered outside of the more popular centers of Manhattan and Brooklyn (though Chinatown and the Lower East Side are still present). This is even more striking when looking at the density map of the Normal People. As the map reveals, the strongest cluster of Normal People are in Brooklyn in the adjoining neighbourhoods to the hippest parts of the borough.

<img src="/paper/img/group-1.png" width="404">
<img src="/paper/img/ClusterNormalPeople.png" width="404">

#####The 2%: 
The 2%, as the name implies, represent only 2% of the listings. These rarefied locations are also the most expensive with an average price of $203 a night. They are also clustered in the wealthiest neighbourhoods with an average median income of around $183,000. Interestingly, this high cost does not result in the highest scores in our custom indicators, with the 2% having the second highest coffee and connectivity scores and second to last beer score. The density map of listings shows the highest concentration of these listings in Midtown East (curiously, not far from Trump Tower).

<img src="/paper/img/group-2.png" width="404">
<img src="/paper/img/Cluster2percent.png" width="404">

#####3) Central Action: 
The Central Action grouping, as the name implies, is very centrally located to the core of Manhattan and the known tourist attractions of the city. This location no doubt contributes to the groupings high price and general wealth, with the second highest average nightly price and median income at $183 and about $111,000, respectively. This central clustering also puts these listings very close to coffee and connectivity, representing the highest coffee score and
connectivity scores of the model. The density map reveals a strong clustering in Soho and Chelsea.


<img src="/paper/img/group-3.png" width="404">
<img src="/paper/img/Clustercentral.png" width="404">



#####4) Hip Kids: 
The Hip Kids, it appears, look for the cheapest tradeoff between accessibility, price, and amenities. Though this grouping has only the third highest price and median income (at $152 a night and about $62,000 a year, respectively) it has the highest beer score (by far) and a relatively high connectivity score and coffee score although
it ranks third in both. As the density map reveals (Figure 12), these listings are concentrated in the known hip centers of the Lower East Side and Williamsburg across the East River. As such, there is likely a correlation between the lower density of areas like Williamsburg and the significantly higher beer score, as breweries require space that is expensive to come buy in Manhattan.

<img src="/paper/img/group-4.png" width="404">
<img src="/paper/img/Clusterhip.png" width="404">

