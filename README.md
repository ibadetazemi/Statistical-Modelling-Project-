Final-Project-Statistical-Modelling-with-Python

Project/Goals

(My project goals are to: Determine the strength of the relationship between number of bikes + POI’s +
1. Connecting to CityBikes API Step 2: Connecting to Foursquare and Yelp APIs, Part 3: Joining Data, Part 4: Building a Model + Results + Challenges + future goals.)

Process

Part 1: Connecting to CityBikes API

Tasks:

1.) Choose a city covered by the CityBikes API and retrieve all available bike stations in that city. 2.) For each bike station, use the API to call the latitude, longitude and number of bikes. Parse the JSON object into a Pandas dataframe. 3.) Complete the city_bikes.ipynb notebook to demonstrate how you executed the tasks above.

Part 2: Connecting to Foursquare and Yelp APIs

Tasks:

1.) Connect to the Foursquare API Connect to the Yelp API. 2.) For each of the bike stations in Part 1, query both APIs to retrieve information for the following in that location: Restaurants or bars Various POIs (points of interest) of your choice 3.) Create a DataFrame for the Yelp results and Foursquare results. 4.) Compare the quality of the Yelp and Foursquare API. For your location, which API gives you the most complete information/better coverage? 5.) Complete the yelp_foursquare_EDA.ipynb notebook to demonstrate how you executed the tasks above.

Part 3: Joining Data

Tasks:

1.) Join the data from Part 1 with the data from Part 2 to create a new dataframe. 2.) Use data visualization to explore the data. 3.) Create your own SQLite database and store the data you've collected on the POIs. 4.) Validate your data. 5.) Complete the joining_data.ipynb notebook to demonstrate how you executed the tasks above.

EDA Visualisations:

# Citybikes_heatmap
sns.heatmap(data= numeric, annot=True)

# Citybikes_whiskers
sns.boxplot(x=citybikes['Distance'], whis=4)

# Citybikes_violin
sns.violinplot(data=citybikes, y="Number of Bikes")
plt.show()

# Citybikes_boxplot
plt.figure(figsize=(6.4,4.8)) #default size
sns.barplot(data=citybikes, x='Ratings', y='Number of Bikes') #averages with error bars

plt.show()

# Citybikes_scatterplot
plt.figure(figsize=(15,8))
sns.scatterplot(data=citybikes, x='Ratings', y='Number of Bikes', hue='Distance', size='Number of Bikes')

plt.show()

# Citybikes_pairplot
fig_5=sns.pairplot(data=citybikes,
                    kind='reg', 
                    diag_kind='kde',
                    plot_kws={'line_kws':{'color':'green'}})
plt.show()

# Citybikes_
fig, axes = plt.subplots(2, 2, figsize=(19, 10))

# Citybikes_histogram
axes[0,0].hist(citybikes['Number of Bikes'])
axes[0,0].set_title('[Matplotlib] Histogram of Number of Bikes')

axes[0,1].boxplot(citybikes['Ratings'])
axes[0,1].set_title('[Matplotlib] Box-Plot of Ratings')

sns.histplot(ax=axes[1,0], data=citybikes, x="Distance")
axes[1,0].set_title('[Seaborn] Histogram of Distance')

sns.boxplot(ax=axes[1,1], data=citybikes, y="Bike Stations")
axes[1,1].set_title('[Seaborn] Box-Plot of Bike Stations')

plt.show()

# Citybikes_plotgraph2
fig_2=sns.scatterplot(data=citybikes,
            y ='Latitude',
            x ='Longitude',
            hue='Ratings',
            size='Ratings',
            sizes=(0, 200))
fig_2.set(title='Restaurants in New York City')

# Citybikes_plotgraph
fig_1=sns.scatterplot(data=citybikes,
            y ='Latitude',
            x ='Longitude',
            hue='Number of Bikes',
            size='Number of Bikes',
            sizes=(0, 200))
fig_1.set(title='Available bikes in New York City')

# Citybikes_scatterplot graph
sns.jointplot(data=citybikes, 
              x="Ratings", 
              y="Number of Bikes",
              height = 8    # a jointplot is a square by default 
            )
plt.suptitle("JoinPlot Comparing Number of Bikes to Ratings", y=1)

plt.show()

Part 4: Building a Model

Tasks:

1.) Build a regression model using Python’s statsmodels module that demonstrates a relationship between the number of bikes in a particular location and the characteristics of the POIs in that location. 2.) Interpret results. Expand on the model output, and derive insights from your model. 3.) Can you think of a way to turn the above regression problem into a classification one? 4.) Complete the model_building.ipynb notebook to demonstrate how you executed the tasks above.

Results

(Fill in what you found about the comparative quality of API coverage in your chosen area and the results of your model: The coverage that I found is that the people in NYC use citibikes quite often and for long periods at a time. The regression model that was built to predict number of bikes, ratings and distance is performing very well.

The low R-squared value appears to reflect that there is a strong correlation
<> Coefficient: Is positive and has a positive affect on Y
<> T-Statistic: Strong coefficient
<> P-Value: Significance of each and is a strong coefficient)

Challenges

(Some challenges that I faced was learning how to use API's, building a regression model as well as time was a challenge.)

Future Goals

(If I had more time I would spend more time on going more in-depth with cleaning data and finding more POI and just adding more POI's.)
