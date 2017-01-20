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

### Day 9: January 11, 2017

**Today's Progress:** Setup a repo for the Leaflet map page of my brewery visits. Created a simple Gulp build process for the site. Did some minor refactoring.

**Thoughts:** Getting quicker on making a new repo. Put the past work in as separate commits. My javascript uses let and const instead of var. This basic part of ES2015 is screwing up the gulp-uglify module.

**Link to work:**
* [myGeoBeerMap](https://github.com/devNoiseConsulting/myGeoBeerMap/)
* [Last commit for the day](https://github.com/devNoiseConsulting/myGeoBeerMap/commit/97a88065fdb918cb75120ab82f9156b171098300Â)
* [breweries.flynnmj.org](http://breweries.flynnmj.org/)

### Day 10: January 12, 2017

**Today's Progress:** Added Bootstrap 4 to make the map page look nicer.

**Thoughts:** Kept searching through the docs for things I knew I could do with Bootstrap 3. Seems I can still use the "small" class to scale down the text in the footer. I couldn't find that mentioned in the new docs. Since my layout is not that complex, still haven't hit to much on the use of Flexbox.

**Link to work:**
* [myGeoBeerMap](https://github.com/devNoiseConsulting/myGeoBeerMap/)
* [Last commit for the day](https://github.com/devNoiseConsulting/myGeoBeerMap/commit/b0c7bdc33df4358ba2327e8da256da8da3692b01)
* [breweries.flynnmj.org](http://breweries.flynnmj.org/)

### Day 11: January 12, 2017

**Today's Progress:** Added an code to use XMLHttpRequest if the Fetch API isn't available in the browser. (Looking at you Apple!) Minor tweaks to the UI around the buttons.

**Thoughts:** I knew that the Fetch API didn't work everywhere. Moving to Bootstrap v4, made testing on mobile bring home that the map wasn't displaying breweries. Need to look into the margin and padding spacing for BootStrap more. Quick fix was to put the class on all the elements. Feels like they should inherit from the column or row div.

**Link to work:**
* [myGeoBeerMap](https://github.com/devNoiseConsulting/myGeoBeerMap/)
* [Commit for the day](https://github.com/devNoiseConsulting/myGeoBeerMap/commit/3cc229781be9a61d282c93a3ea4d7778be04ce62)
* [breweries.flynnmj.org](http://breweries.flynnmj.org/)

### Day 12: January 16, 2017

**Today's Progress:** Moved to clustered markers to make the map look less cluttered. Gulp task to download brewery list.

**Thoughts:** Back from vacation, so I missed a few days. The cluster plugin was very easy to integrate into the code. Minor issue with the cluster CSS. GitHub outage last week, made having a local copy a good idea.

**Link to work:**
* [myGeoBeerMap](https://github.com/devNoiseConsulting/myGeoBeerMap/)
* [Commit for the day](https://github.com/devNoiseConsulting/myGeoBeerMap/commit/316a910279d6c71d1b7ca5db52c6c8ff3cb1da3c)
* [breweries.flynnmj.org](http://breweries.flynnmj.org/)

### Day 13: January 17, 2017

**Today's Progress:** Started working on making myGeoBeerMap a Progressive Web App.

**Thoughts:** Getting a manifest.json for myGeoBeerMap. Created an app icon and generated the various sizes. Modified the gulp tasks to copy the manifest and images.

**Link to work:**
* [myGeoBeerMap](https://github.com/devNoiseConsulting/myGeoBeerMap/)
* [Commit for the day](https://github.com/devNoiseConsulting/myGeoBeerMap/commit/33e1a607457da7ab43ff4d98f7d42bf889139b13)
* [breweries.flynnmj.org](http://breweries.flynnmj.org/)

### Day 14: January 18, 2017

**Today's Progress:** Swapped out the default css for the cluster markers with css that has a color scheme that matches the visited brewery color (#0047AB).

**Thoughts:** When changing color schemes, you can fall down a rabbit hole. New cluster marker colors lead to changing the colors on the individual markers. This was done in the code as I didn't want to modify all the geoJSON files in the geoBeer repo.

**Link to work:**
* [myGeoBeerMap](https://github.com/devNoiseConsulting/myGeoBeerMap/)
* [Commit for the day](https://github.com/devNoiseConsulting/myGeoBeerMap/commit/379f286e478aff0dc64f6a7a5f8787a7ea7b6254)
* [breweries.flynnmj.org](http://breweries.flynnmj.org/)

### Day 15: January 19, 2017

**Today's Progress:** Added Favicons and social media meta data. Changed the footer so that it would stick to the bottom of the browser. Tweaked the color and icon remapping.

**Thoughts:** Bootstrap v4's container-fluid and padding were messing up the sticky footer. Facebook seems to have cached the og:image. Making it hard to test the new image size.

**Link to work:**
* [myGeoBeerMap](https://github.com/devNoiseConsulting/myGeoBeerMap/)
* [Commit for the day](https://github.com/devNoiseConsulting/myGeoBeerMap/commit/e10c206ca5652f615ee073fcc6be7fc6e055914c)
* [breweries.flynnmj.org](http://breweries.flynnmj.org/)


### Day 0: February 30, 2016 (Example 1)
##### (delete me or comment me out)

**Today's Progress**: Fixed CSS, worked on canvas functionality for the app.

**Thoughts:** I really struggled with CSS, but, overall, I feel like I am slowly getting better at it. Canvas is still new for me, but I managed to figure out some basic functionality.

**Link to work:** [Calculator App](http://www.example.com)
