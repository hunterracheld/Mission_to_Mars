# Mission to Mars

This project contains scripts to build a web application that scrapes various websites for data related to Mars and displays the information in a single HTML page. 

### 1. Web Scraping. `mission_to_mars.ipynb` contains code to complete all scraping and analysis tasks:
- NASA Mars News - Scrapes (https://mars.nasa.gov/news/) and collects the latest News Title and Paragraph Text. 

- JPL Mars Space Images - Visits the url for JPL Featured Space Image (https://www.jpl.nasa.gov/spaceimages/?search=&category=Mars), uses splinter to navigate the site and find the image url for the current Featured Mars Image 

- Mars Weather - Visits the Mars Weather twitter account (https://twitter.com/marswxreport?lang=en) and scrapes the latest Mars weather tweet from the page 

- Mars Facts - Visits the Mars Facts webpage (https://space-facts.com/mars/) and use Pandas to scrape the table containing facts about the planet including Diameter, Mass, etc

- Mars Hemispheres - Visit the USGS Astrogeology site https://astrogeology.usgs.gov/search/results?q=hemisphere+enhanced&k1=target&v1=Mars) to obtain high resolution images for each of Mar's hemispheres

- - -

### 2. - MongoDB and Flask Application with MongoDB with Flask templating is used to create a new HTML page that displays all of the information that was scraped from the URLs above

- `scrape_mars.py` is the converted Jupyter notebook with a function called `scrape` that will execute all of the scraping code from above and return one Python dictionary containing all of the scraped data

- `mars_app.py` includes a `/scrape` route that imports the `scrape_mars.py` script and calls the `scrape` function

- returned values are in Mongo as a Python dictionary

- a root route `/` will query the Mongo database and pass the mars data into an HTML template to display the data

- `index.html` will take the mars data dictionary and display all of the data in the appropriate HTML elements


