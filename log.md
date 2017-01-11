# 100 Days Of Code - Log

### Day 1: January 3, 2017

**Today's Progress:** Used [Leaflet.js](http://leafletjs.com/) to display my geoJSON data for breweries.

**Thoughts:** Still doing a bit of copy and paste coding to get this work as I scanned tutorials and docs. Needed to sign up with [Mapbox](https://www.mapbox.com/) so you have map tiles to render. Couldn't get code to change the color of the marker for the breweries.

**Link to work:** [geoBeer Map #1](http://breweries.flynnmj.org/leaflet_20170103.html)

### Day 2: January 4, 2017

**Today's Progress:** More [Leaflet.js](http://leafletjs.com/) coding. Changed to circle markers so that I could provide color and size to the markers. Used an ES6 template string to create an HTML fragment for the marker's popup. This let me bold the brewery name and link to their website.

**Thoughts:** Started out trying to use Leaflet.vector-markers, but couldn't get around the following error:

`Uncaught (in promise) DOMException: Failed to execute 'add' on 'DOMTokenList': The token provided must not be empty`

Need to look into the `pointToLayer` option for the `L.geoJSON` call.  


**Link to work:** [geoBeer Map #2](http://breweries.flynnmj.org/leaflet_20170104.html)

### Day 3: January 5, 2017

**Today's Progress:** More [Leaflet.js](http://leafletjs.com/) coding. Was able to get the Leaflet.vector-markers to work. Went with Font Awesome for the marker icons.

**Thoughts:** Started out trying to use the Maki icons, but couldn't find a quick way to include them. Tried out both the Bootstrap/Glyphicons and Font Awesome icons. Was easier to switch between those icons sets. Ended up on Font Awesome as it has a beer icon like the Maki icon set. I could pull the marker-symbol from the the geoJSON feature properties. Haven't been able to figure out if I can scale the vector markers like I did for with the circle markers.

Believe I figured out why I was getting DOMExceptions yesterday. With no CSS for the icon information, so the code couldn't find any styles for the icon I was trying to reference.

**Link to work:** [geoBeer Map #3](http://breweries.flynnmj.org/leaflet_20170105.html)

### Day 4: January 6, 2017

**Today's Progress:** More [Leaflet.js](http://leafletjs.com/) coding. Trying to filter the breweries. Added buttons to filter the breweries from the map. Also added a search box to filter breweries by their name.

**Thoughts:** Moved some code into a function since it would be used in other functions. Also made some global variables for the brewery data and the map layer. This allowed me to remove the breweries from the map before I filtered them. Otherwise you couldn't tell the filters were doing any work.

**Link to work:** [geoBeer Map #4](http://breweries.flynnmj.org/leaflet_20170106.html)

### Day 5: January 7, 2017

**Today's Progress:** Started building a script to use Facebook's Graph API to find breweries. Made a function to do a place search and another function to get information about the place.

**Thoughts:** Had to skim through the docs a couple times to figure out how to get an access token. Using the Graph API Explorer to figure out what fields I need.

**Link to work:** [fbPlaceSearch](https://github.com/devNoiseConsulting/fbPlaceSearch)

### Day 6: January 8, 2017

**Today's Progress:** Pulled more fields in from the Graph API and converting places into geoJSON.

**Thoughts:** The Graph API Explorer is letting me use a greater distance than what my code is allowed to use. Will need to look into Promises because figure when all the API calls are done before doing a final geoJSON conversion. Also need to figure out how filter out the false positives. Stuff in Brewerytown may not be a brewery, but come back in the results.

**Link to work:** [fbPlaceSearch](https://github.com/devNoiseConsulting/fbPlaceSearch/commit/dd8397c405436ae9b62eb1bdb4edd8406a481cf2)

### Day 7: January 9, 2017

**Today's Progress:** Getting git repo setup for fbPlaceSearch. Getting from APP_ID and APP_SECRET from the environment variables.

**Thoughts:** Always end up committing the code with the keys hard coded. Even though I was trying to avoid that this time. Ended up deleting the app and recreating it. Put the keys in a .env file. Couldn't get the `npm run setenv` to stick, dropping back to just sourcing the .env file.

**Link to work:** [fbPlaceSearch](https://github.com/devNoiseConsulting/fbPlaceSearch/commit/50a10c2b49520d602f8746eee3394d3b2a8cf513)

### Day 8: January 10, 2017

**Today's Progress:** Worked on getting multiple searches to run concurrently. Started a Facebook page post script.

**Thoughts:** Still don't seem to get all the places I expect. Maybe the API and not the code. Running into OAuth errors when trying to make a POST to my page's feed.

**Link to work:** [fbPlaceSearch](https://github.com/devNoiseConsulting/fbPlaceSearch/commit/3b4ad67a6944682cb0a9aca83903f196011caebd)

### Day 0: February 30, 2016 (Example 1)
##### (delete me or comment me out)

**Today's Progress**: Fixed CSS, worked on canvas functionality for the app.

**Thoughts:** I really struggled with CSS, but, overall, I feel like I am slowly getting better at it. Canvas is still new for me, but I managed to figure out some basic functionality.

**Link to work:** [Calculator App](http://www.example.com)
