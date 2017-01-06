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

### Day 2: January 5, 2017

**Today's Progress:** More [Leaflet.js](http://leafletjs.com/) coding. Was able to get the Leaflet.vector-markers to work. Went with Font Awesome for the marker icons.

**Thoughts:** Started out trying to use the Maki icons, but couldn't find a quick way to include them. Tried out both the Bootstrap/Glyphicons and Font Awesome icons. Was easier to switch between those icons sets. Ended up on Font Awesome as it has a beer icon like the Maki icon set. I could pull the marker-symbol from the the geoJSON feature properties.

Believe I figured out why I was getting DOMExceptions yesterday. With no CSS for the icon information, so the code couldn't find any styles for the icon I was trying to reference. 

**Link to work:** [geoBeer Map #3](http://breweries.flynnmj.org/leaflet_20170105.html)


### Day 0: February 30, 2016 (Example 1)
##### (delete me or comment me out)

**Today's Progress**: Fixed CSS, worked on canvas functionality for the app.

**Thoughts:** I really struggled with CSS, but, overall, I feel like I am slowly getting better at it. Canvas is still new for me, but I managed to figure out some basic functionality.

**Link to work:** [Calculator App](http://www.example.com)
