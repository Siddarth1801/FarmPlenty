
## Inspiration

In the past year, I've talked to many farmers and learned how hard it can be for them to make a living. Farmers have to deal with unpredictable weather, changing consumer demand, and endless pests and weeds. And while they are struggling to stay in business, they also have to take good care of the land and soil for future generations. The USDA has a wealth of data on crops and prices that can help farmers. The challenge is making it relevant for their own local circumstances. I decided to use my own extensive experience in data analysis and app development to create a better way for farmers to visualize the crop and price information most important to them. Showing all this information on a map makes this information easy to browse and understand.


## How I built it

I wanted to create an app that works well on both desktop and mobile devices. I chose to use Bootstrap to lay out the UI because it adapts well to different screen sizes. The Django backend requests NASS CropScape data using the Microsoft Azure API. I preprocessed the NASS Quickstats data to store crop price information in a SQLite database. The frontend uses Angular.js to request data from the backend and update the UI. I used Angular Google Maps to create the interactive map. The graphs are drawn using Angular Charts.

## Challenges I ran into

The crop names in the NASS CropScape data don't exactly match the commodity names in the NASS Quickstats data. In addition, some of the CropScape crops are double crops. To deal with this, I had to create a mapping from CropScape crop names to Quickstats commodity names so I could cross reference the two two data sets in my app.

Parsing the Quickstats data was also a challenge. There are so many types of data included in this data set, from prices to farm practices to farmer demographic information. Also, there was no documentation about the values of many of the fields. For example, prices are usually given in dollars per unit weight, but sometimes they also represented percent parity prices. The Farm Data Dashboard helped me understand how to find the data I needed, but it still required quite a bit of trial and error to determine the precise queries.

It took some work to integrate all the various frontend UI frameworks including Angular.js, Bootstrap, Angular Google Maps, and Angular Charts so that the final result works properly and looks clean in both mobile and desktop environments. I had to modify Angular Charts a bit and customize some of the CSS.

## Accomplishments that I'm proud of

* Learning Angular.js for this project.
* Creating a responsive app that works well in both desktop and mobile browsers.
* Looking up CropScape data using Google Maps.


## What's next for FarmPlenty Local Crop Trends

My original idea was to develop an app to help farmers better understand the tradeoffs of organic and conventional farming. I was hoping to find more information about pricing of organic vs. conventional crops, but was not able to find this in the NASS data. I would love to find this data and incorporate it into the app.

I would like to improve the crop visualization, perhaps by displaying the top crops as an overlay on the map. I want to hear more feedback from farmers to find out what features are most useful. I would also like to do more sophisticated analysis of the data to derive more useful insights for farmers.


# Installation

Install Django and put this into your Django directory. You will need to update a few strings in settings.py to have the correct path and site key. You will also need to update cropmap.js with your Google Maps API key. It has been tested with Django 1.4 and 1.8 with Python 2.7.
