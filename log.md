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

### Day 16: January 20, 2017

**Today's Progress:** Revisited the padding/margins on the buttons. Move the form elements into an input-group.

**Thoughts:** Not sure what I changed, but the padding/margins for the buttons are working. Before the buttons would be touching and looked wrong. So I have been using the mr-2 and mb-3 classes to space them apart. Tested out putting the buttons in a button group, be decide against it. Likewise, I tried toggle states on the buttons with the same conclusion.
Changes the submit over to a button with the Font Awesome search icon. This caused me to rework the filterBreweries to handle a click event in addition to the submit event.

**Link to work:**
* [myGeoBeerMap](https://github.com/devNoiseConsulting/myGeoBeerMap/)
* [Commit for the day](https://github.com/devNoiseConsulting/myGeoBeerMap/commit/254d06d81faac1a5360df9f1540940b377f6dca9)
* [breweries.flynnmj.org](http://breweries.flynnmj.org/)

### Day 17: January 22, 2017

**Today's Progress:** Wrote some small scripts to process the brewery files into a more neutral state.

**Thoughts:** Added UUIDs to each of the locations a brewery might have. This should allow other users to identify where they have made brewery visits. I was able to extract my status and save it to a separate file. With this save, I can reset all the brewery locations to a default state.

**Link to work:**
* [geoBeer](https://github.com/devNoiseConsulting/geoBeer/)
* [Commit for the day](https://github.com/devNoiseConsulting/geoBeer/commit/b7b16e1e6acab7a58e295afdb05acef8a131c762)

### Day 18: January 23, 2017

**Today's Progress:** Created a script that will generate the myBreweryList.geojson from my
geobeer.json file in the myGeoBeerMap. Updated the package.json to have script command to run the generation. The gulpfile.js was modified to exec the script so the myBreweryList.geojson can be created from a task.

**Thoughts:** This should allow other people to contribute breweries to the geoBeer repo with affecting my brewery visits. First time I added one of my github repositories as a dependency. Will need to look into how I version geoBeer so myGeoBeerMap will know to pull a newer version of the repository.

**Link to work:**
* [myGeoBeerMap](https://github.com/devNoiseConsulting/myGeoBeerMap/)
* [Commit for the day](https://github.com/devNoiseConsulting/myGeoBeerMap/commit/e3ab0b280b4bc3ba07351392119c953f4b8f6e6e)

### Day 19: January 24, 2017

**Today's Progress:** Added a Near Me radius marker to myGeoBeerMap to help identify the breweries that are close to you.

**Thoughts:** Multiple clicks on the "Near Me" button would cycle through the different radii or turn the marker off. Simple error with resetting the radii index variable cause the first radius to be skipped after going though all the radii.

**Link to work:**
* [myGeoBeerMap](https://github.com/devNoiseConsulting/myGeoBeerMap/)
* [Commit for the day](https://github.com/devNoiseConsulting/myGeoBeerMap/commit/ed38f129db1de1ea3f5fd2469f959d5c37b61391)
* [breweries.flynnmj.org](http://breweries.flynnmj.org/)

### Day 20: January 25, 2017

**Today's Progress:** When using the "Near Me" feature the map will also pan to the user's location. Tweaked the radius marker opacity. Fix a bug to prevent 2 radius markers being on the map.

**Thoughts:** Seems that the navigator.geolocation.watchPosition would be called multiple times or again when returning to the tab. This would cause the code to lose reference to the radius marker so it couldn't be removed.

**Link to work:**
* [myGeoBeerMap](https://github.com/devNoiseConsulting/myGeoBeerMap/)
* [Commit for the day](https://github.com/devNoiseConsulting/myGeoBeerMap/commit/6515fdc49a0dac96e6b6f5de2b5959e803237e62)
* [breweries.flynnmj.org](http://breweries.flynnmj.org/)

### Day 21: January 26, 2017

**Today's Progress:** Signed up with freeCodeCamp and started working on the Front End Development Certification. Ran through the HTML5 and CSS section.

**Thoughts:** Very similar to the Codecademy work flow. Mostly a review of the HTML that I already know.

**Link to work:**
* [freeCodeCamp Profile](https://www.freecodecamp.com/devnoiseconsulting)

### Day 22: January 27, 2017

**Today's Progress:** Finished more freeCodeCamp challenges (BootStrap and jQuery) and completed the first two projects.

**Thoughts:** I have used BootStrap for a couple projects, and have used version 4 on myGeoBeerMap. I touch on jQuery a bit, but have less experience with it. Most modern browser can do most of the same things with vanilla javascript. Threw up some minimal projects in CodePen so I could move on.

**Link to work:**
* [freeCodeCamp Profile](https://www.freecodecamp.com/devnoiseconsulting)

### Day 23: January 28, 2017

**Today's Progress:** Started the freeCodeCamp challenges for Basic Javascript.

**Thoughts:** Lots of similar concepts I learned in other languages.

**Link to work:**
* [freeCodeCamp Profile](https://www.freecodecamp.com/devnoiseconsulting)

### Day 24: January 29, 2017

**Today's Progress:** Finished the freeCodeCamp challenges for Basic Javascript and started/finished the Object Oriented and Functional Programming challenges.

**Thoughts:** Ran through a lot of stuff I was familar with. Since mode coding was involved, I did have to slow down and make sure I knew what was required.

**Link to work:**
* [freeCodeCamp Profile](https://www.freecodecamp.com/devnoiseconsulting)

### Day 25: January 30, 2017

**Today's Progress:** Started the freeCodeCamp challenges for Basic Algorithms.

**Thoughts:** These are taking a bit more time to complete. Dropped back to coding in vim so I could run the code through node.js on the command line.

**Link to work:**
* [freeCodeCamp Profile](https://www.freecodecamp.com/devnoiseconsulting)

### Day 26: January 31, 2017

**Today's Progress:** Finished the freeCodeCamp challenges for Basic Algorithms. Then went back to myGeoBeerMap to added a bounding box to search results.

**Thoughts:** Coded the algorithms in a manner I'm used to. Later in the day I thought I could used a .split().map().join() instead of a for loop. After using the search on myGeoBeerMap, I felt should center around and show all the results. That pushed me into using the .reduce() function to get the data I needed.

**Link to work:**
* [freeCodeCamp Profile](https://www.freecodecamp.com/devnoiseconsulting)
* [myGeoBeerMap](https://github.com/devNoiseConsulting/myGeoBeerMap/)
* [Commit for the day](https://github.com/devNoiseConsulting/myGeoBeerMap/commit/f4c6d333c6df23e2b7b8796fd4c5baadb4d42b0b)
* [breweries.flynnmj.org](http://breweries.flynnmj.org/)


### Day 27: February 1, 2017

**Today's Progress:** Finished the freeCodeCamp challenges for JSON and API. Completed one of the Intermediate Front End Development Projects. Also added a bounding box feature to the Near Me link for myGeoBeerMap.

**Thoughts:** Felt I spent to much time searching for a quote API to use instead of actually coding the project. For myGeoBeerMap, kept tweaking the calculation of the bounding box to figure out best fit.

**Link to work:**
* [freeCodeCamp Profile](https://www.freecodecamp.com/devnoiseconsulting)
* [CodePen](http://codepen.io/_dev_noise/pen/BpraoP)
* [myGeoBeerMap](https://github.com/devNoiseConsulting/myGeoBeerMap/)
* [Commit for the day](https://github.com/devNoiseConsulting/myGeoBeerMap/commit/28c306c005fea2d01ac170b04751ec5fcf44094f)
* [breweries.flynnmj.org](https://breweries.flynnmj.org/)

### Day 28: February 2, 2017

**Today's Progress:** Completed the second of the Intermediate Front End Development Projects.

**Thoughts:** Still spent a chunk of time trying to figure out which API to use. Wrote this project without using jQuery. Cribbed some code from myGeoBeerMap site to handle the lower parts of the AJAX calls.

**Link to work:**
* [freeCodeCamp Profile](https://www.freecodecamp.com/devnoiseconsulting)
* [CodePen](http://codepen.io/_dev_noise/pen/ZLxVKe)

### Day 29: February 3, 2017

**Today's Progress:** Completed the third of the Intermediate Front End Development Projects.

**Thoughts:** Had a specific API to use for this project which was nice. Unfortunately, the docs seemed a bit weak. My query still came was cribbed from a search result. Hit a CORS issue with my search, found the solution in the freeCodeCamp forums. Safari is a semi modern browser. Apple needs to get on the ball and implement some of the newer features (the fetch API and template literals come to mind).

**Link to work:**
* [freeCodeCamp Profile](https://www.freecodecamp.com/devnoiseconsulting)
* [CodePen](http://codepen.io/_dev_noise/pen/qRYpRp)

### Day 30: February 4, 2017

**Today's Progress:** Completed the fourth of the Intermediate Front End Development Projects.

**Thoughts:** Would have been nice if I could have request all the information in one call instead of 2x. Since I couldn't figure out when all the API calls were done, manipulated the DOM (2x-1) more times than I should have. Went with vanilla JS, but that means my project won't work in Safari. Presentation could be a little better, but I prefer to focus on the functionality.

**Link to work:**
* [freeCodeCamp Profile](https://www.freecodecamp.com/devnoiseconsulting)
* [CodePen](http://codepen.io/_dev_noise/pen/rjKxpj)

### Day 31: February 5, 2017

**Today's Progress:** Completed seven of the Intermediate Algorithm challenges.

**Thoughts:** Some good challenges to tackle today. To keep the algorithm for the roman numeral challenge simple I made array for translation hold my edge cases. That way I didn't have to test for them. Also went with regex for the pig latin challenge. Think that made it easier to determine what type of translation I needed to perform.

**Link to work:**
* [freeCodeCamp Profile](https://www.freecodecamp.com/devnoiseconsulting)

### Day 32: February 6, 2017

**Today's Progress:** Completed another seven of the Intermediate Algorithm challenges.

**Thoughts:** These challenges get me thinking. Always need to test. An off by one bug showed up a couple times today.

**Link to work:**
* [freeCodeCamp Profile](https://www.freecodecamp.com/devnoiseconsulting)

### Day 33: February 7, 2017

**Today's Progress:** Completed the rest of the Intermediate Algorithm challenges.

**Thoughts:** The Streamroller challenge was the toughest challenge yet. Tried to go with recursion, but somehow managed to lose the 2nd element in the array. After searching to forums, found some hints that pointed me at using Array.reduce to come up with a solution. A search also turned up parseInt(x, 2) that help make quick work of the binary string to normal string.

**Link to work:**
* [freeCodeCamp Profile](https://www.freecodecamp.com/devnoiseconsulting)

### Day 34: February 8, 2017

**Today's Progress:** Completed three of the Advanced Algorithm challenges.

**Thoughts:** I had to work at these challenges, but they were more straight forward than Streamroller. The symmetric difference took a couple tries to get right. Had to dedup the numbers in the array before attempting to figure out the symmetric difference. The cash register was a bit like the roman numerial challenge. Start with the highest currency and go down to make the change.

**Link to work:**
* [freeCodeCamp Profile](https://www.freecodecamp.com/devnoiseconsulting)

### Day 35: February 9, 2017

**Today's Progress:** Completed three more of the Advanced Algorithm challenges.

**Thoughts:** The Inventory Update challenge was pretty straight forward. Just had to go back and add an sort to the inventory. The No repeats please challenge was hard. Tried to go at it by calculating the number of permutations. Search for some help and found Heap's algorithm. The brute force method solved it. The Friendly Date Ranges challenge wasn't to bad. Though I had to keep tweaking the test cases. Seems like I had to make exceptions for the year 2016.

**Link to work:**
* [freeCodeCamp Profile](https://www.freecodecamp.com/devnoiseconsulting)

### Day 36: February 10, 2017

**Today's Progress:** Finished the Advanced Algorithm challenges.

**Thoughts:** All pretty straight forward chanllenges today. The instanceof part of the Make a Person challenge had me rework my solution. For Map the Debris challenge, I pulled the formula from the linked Wikipedia page. Forgot to add Earth's radius and round the answer before I passed the challenge. The Pairwise challenge had some hurdles to get over. Had to revise how I was tracking the used indicies and also make sure I wasn't using the same index for both parts of the sum.

**Link to work:**
* [freeCodeCamp Profile](https://www.freecodecamp.com/devnoiseconsulting)

### Day 37: February 11, 2017

**Today's Progress:** Finished the first Advanced Front End Development Projects. Have a working JavaScript Calculator.

**Thoughts:** Built with Vanilla JavaScript and BootStrap. Took a little bit of time to get it all wired up, but was mostly straight forward. Was trying to convert the number from a string value to a numerical value when the user clicked on a number button. To avoid errors, this conversion was done when a math operator was clicked. The other big bug was handling multiple presses on the equals button. Put in some checks to prevent the register values from becoming corrupted. Converting null to a int or float would result in NaN.

**Link to work:**
* [freeCodeCamp Profile](https://www.freecodecamp.com/devnoiseconsulting)
* [CodePen](http://codepen.io/_dev_noise/pen/MJZgbM)

### Day 38: February 12, 2017

**Today's Progress:** Finished the second Advanced Front End Development Projects. Still can't pronounce pomodoro.

**Thoughts:** Built with Vanilla JavaScript and BootStrap. Working with the Date object can be a pain. Bit of effort to get the clock display to switch between the two timers. Can't use the reduce function on a NodList and had to drop back to a forEach. Also need to clear the timeout so that I didn't end up with multiple timeouts running.

**Link to work:**
* [freeCodeCamp Profile](https://www.freecodecamp.com/devnoiseconsulting)
* [CodePen](http://codepen.io/_dev_noise/pen/MJZryr)


### Day 39: February 13, 2017

**Today's Progress:** Made a Tic Tac Toe game to finished the third Advanced Front End Development Project.

**Thoughts:** Minimal UI using BootStrap. Getting the UI wired up is getting fairly straight forward. How to handle playing was a bit harder. Trying to get the AI portion of the game working was hard. Went through a couple revisions to figure out all the conditions I wanted to check for to figure out the best square. Had to tack on some code to just pick a square if there is no best square.

**Link to work:**
* [freeCodeCamp Profile](https://www.freecodecamp.com/devnoiseconsulting)
* [CodePen](http://codepen.io/_dev_noise/pen/dNwLNE)

### Day 40: February 14, 2017

**Today's Progress:** Started on the Simon Game for the fourth Advanced Front End Development Project.

**Thoughts:** More BootStrap for the UI and Vanilla JavaScript. Tried to use some libraries to handle a toggle switch. UI looked good, but couldn't get click events to get to my functions. Dropped back to using button groups and some cutom Javascript to add/remove classes to perform the toggle. Game squares will change color and play a sound.

**Link to work:**
* [freeCodeCamp Profile](https://www.freecodecamp.com/devnoiseconsulting)
* [CodePen](http://codepen.io/_dev_noise/pen/bgZbqY)

### Day 41: February 15, 2017

**Today's Progress:** More work on the Simon Game for the fourth Advanced Front End Development Project.

**Thoughts:** Mostly wiring up the UI to the JavaScript. To test, I created a mock sequence to see how playing the sequence would work. Have a stub function to check the players sequence to the computer's. This is most likely where my work will pick up tomorrow. Found myself trying to make sure I use the reduce and forEach functions on an array instead of a plain for loop.

**Link to work:**
* [freeCodeCamp Profile](https://www.freecodecamp.com/devnoiseconsulting)
* [CodePen](http://codepen.io/_dev_noise/pen/bgZbqY)

### Day 42: February 16, 2017

**Today's Progress:** Focused on the sequence logic on the Simon Game for the fourth Advanced Front End Development Project. A little bit of color tweaking for the UI.

**Thoughts:** The sequence check is working. Have the code adding a new square for the sequence. Will play the sequence again if a wrong square is pressed. Don't seem to have an error sound to play. Need to add some code to determine if the user has won the game.

**Link to work:**
* [freeCodeCamp Profile](https://www.freecodecamp.com/devnoiseconsulting)
* [CodePen](http://codepen.io/_dev_noise/pen/bgZbqY)

### Day 43: February 17, 2017

**Today's Progress:** Finished the Simon Game for the fourth Advanced Front End Development Project. That means I've completed the course and received freeCodeCamp's Front End Development Certification.

**Thoughts:** Added a lot of the condition checks(victory, strict mode,game on). Also refactored a some code into their own functions. This was for duplicate code and help clean some functions up.

**Link to work:**
* [freeCodeCamp Profile](https://www.freecodecamp.com/devnoiseconsulting)
* [CodePen](http://codepen.io/_dev_noise/pen/bgZbqY)

### Day 44: February 18, 2017

**Today's Progress:** Just a couple challenges at freeCodeCamp. Big one was doing the how-to-npm challenge.

**Thoughts:** Spent a lot of time trying to get Magento setup on my Ubuntu server. So to get my hour in, I started some of the challenges for the Back End Development Certification. Mostly review, but the tag stuff was something I haven't used before.

**Link to work:**
* [freeCodeCamp Profile](https://www.freecodecamp.com/devnoiseconsulting)
* [Cloud 9](https://c9.io/devnoise/npm)

### Day 45: February 19, 2017

**Today's Progress:** Finished the Start a Nodejs Server challenge at freeCodeCamp.

**Thoughts:** Made today a light day as I had a couple of other thing happening today. Continuing the Back End Development Certification. This is a refresher as I've already completed learnyournode at a nodeschool event.

**Link to work:**
* [freeCodeCamp Profile](https://www.freecodecamp.com/devnoiseconsulting)
* [Cloud 9](https://c9.io/devnoise/learnyournode)

### Day 46: February 20, 2017

**Today's Progress:** Finished the Continue working with Nodejs Servers challenge at freeCodeCamp.

**Thoughts:** Another light day, not as much coding as I would have liked. Feel like I learn how to use code is by looking at examples. Looking at the Node docs didn't always help me.

**Link to work:**
* [freeCodeCamp Profile](https://www.freecodecamp.com/devnoiseconsulting)
* [Cloud 9](https://c9.io/devnoise/learnyournode)

### Day 47: February 21, 2017

**Today's Progress:** Completed freeCodeCamp's Finish working with Nodejs Servers challenge. Also worked on getting Magento installed.

**Thoughts:** Had to reinstall Magento and then had to fix the Apache2 config. Finished the learnyounode tasks. Mostly the HTTP server calls, tripped up when to set the response object.

**Link to work:**
* [freeCodeCamp Profile](https://www.freecodecamp.com/devnoiseconsulting)
* [Cloud 9](https://c9.io/devnoise/learnyournode)

### Day 48: February 22, 2017

**Today's Progress:** Progressed through the first six sections for Unit 1 of Fundamentals of Magento 2 Development v2.1. Wrote a shell script to help me install Magento in case it gets screwed up.

**Thoughts:** Some of the exercise seem to fubar my install of Magento. I can't seem to find the exercise guide. All I have is the solutions guide. Hard for me to know exactly what the exercise was. Also the exercises seem to lack consistency.

**Link to work:**
* [Magento Install](https://magento.home.ts/)
* [mkMagento.sh](https://gist.github.com/devNoiseConsulting/ea5e3eabf7fb8daf47441168a9f7bd90)

### Day 49: February 23, 2017

**Today's Progress:** Started working on Build Web Apps with Expressjs. Also made a gist to display my magento install script.

**Thoughts:** Got through the first challenge and then hit a wall. The Jade challenge isn't working. Peaked at the solution and my code is similar. Somehow Jade didn't get installed. Went with the Read-Search-Ask to find a solution. Searching didn't give offer much. Tried the gitter without success. Created a new topic on the forum. Waiting to hear back. May also just run expresswork on my laptop.

**Link to work:**
* [Cloud 9](https://c9.io/devnoise/express)

### Day 50: February 24, 2017

**Today's Progress:** Forked redrock/expressworks and merge from the azat-co/expressworks. Created an GutHub issue to see if expressworks can be updated.

**Thoughts:** After setting a remote azat-co/expressworks, I was able to do the pull and merge. Ended up with 1 conflict. Apparently since freeCodeCamp forked expressworks for work with Cloud 9, azat-co have updated the code to match most of the timeouts in the exercises. The stylish_css exercise was the only conflict because that exercise was increased to 2000 milliseconds. Since it looked like azat-co/exporessworks should be compatible, I opened an issue with fcc-expressworks to change when they get expressworks from.

**Link to work:**
* [devNoiseConsulting/expressworks](https://github.com/devNoiseConsulting/expressworks)
* [fcc-expressworks issue](https://github.com/freeCodeCamp/fcc-expressworks/issues/8)

### Day 51: February 25, 2017

**Today's Progress:** Finished freeCodeCamp's Build Web Apps with Expressjs. Attended Philly.Net's Code Camp 2017.1.

**Thoughts:** Created a new workspace on Cloud 9 and use the official expressworks module. Still had to install the Pug module to the Jade/Pug challenge to work. Had issues with the last two challenges as the JSON output was multi line and the exercise expected it on a single line. Tweaking the response object to use JSON.stringify solved the problem.

**Link to work:**
* [freeCodeCamp Profile](https://www.freecodecamp.com/devnoiseconsulting)
* [Cloud 9](https://c9.io/devnoise/expressworks)
* [Code Camp 2017.1](https://www.meetup.com/Philly-NET/events/237291594/)

### Day 52: February 26, 2017

**Today's Progress:** Completed freeCodeCamp's Save your Code Revisions Forever with Git.

**Thoughts:** A moderate user of git, then git-it exercises were pretty easy. In fact I've already completed git-it once before.

**Link to work:**
* [freeCodeCamp Profile](https://www.freecodecamp.com/devnoiseconsulting)
* [patchwork](https://github.com/devNoiseConsulting/patchwork)
* [Cloud 9](https://ide.c9.io/devnoise/git-it)

### Day 53: February 27, 2017

**Today's Progress:** Worked on freeCodeCamp's Store Data in MongoDB and completed
Get Set for our API Development Projects.

**Thoughts:** learnyoumongo is not fully baked. It's a bit hard to figure out what needs to be done. The last two exercises weren't finished because mongodb didn't seem to get initialized with the right values. Also had a problem with the module having an hard error instead of catching it because the function done was not defined.

**Link to work:**
* [freeCodeCamp Profile](https://www.freecodecamp.com/devnoiseconsulting)
* [Cloud 9](https://ide.c9.io/devnoise/learnyoumongo)
* [Cloud 9](https://ide.c9.io/devnoise/camper-api-project)
* [learnyoumongo issue](https://github.com/evanlucas/learnyoumongo/issues/55)
* [freeCodeCamp forum post](https://forum.freecodecamp.com/t/learnyoumongo-remove-exercise-broken/91859)

### Day 54: February 28, 2017

**Today's Progress:** Completed freeCodeCamp's Timestamp Microservice project.

**Thoughts:** This was pretty straight forward and reference some of the code from the expressworks exercises. Using toLocaleDateString allowed me to use Vanilla Javascript and not need any custom code for formatting.

**Link to work:**
* [freeCodeCamp Profile](https://www.freecodecamp.com/devnoiseconsulting)
* [timestamp repo](https://github.com/devNoiseConsulting/timestamp)
* [Cloud 9](https://ide.c9.io/devnoise/camper-api-project)

### Day 55: March 1, 2017

**Today's Progress:** Worked a function to validate a magic square as part of a daily programmer challenge. Also updated the myBreweries.js to generate a brewery list file that only includes the brewers that are in the geobeer.json data file.

**Thoughts:** Taking a light day and worked on some features for someone who wants to fork myGeoBeerMap.

**Link to work:**
* [Magic Square Gist](https://gist.github.com/devNoiseConsulting/24c767482638fefa4c6ed8dc4b3d1bcc)
* [myGeoBeerMap](https://github.com/devNoiseConsulting/myGeoBeerMap/)

### Day 56: March 2, 2017

**Today's Progress:** Completed freeCodeCamp's Request Header Parser Microservice. Also deployed both the microservices that I've created so far to Heroku.

**Thoughts:** The Request Header Parser was pretty basic, just pulling some values out of the request object. Got the software by spliting the user-agent string. Found an answer on StackOverflow for getting the IP address. For Heroku, Profile didn't seem to be enough. Adding a "start" and "engine" entry to package.json seem to get things going.

**Link to work:**
* [freeCodeCamp Profile](https://www.freecodecamp.com/devnoiseconsulting)
* [timestamp microservice](https://pure-river-38627.herokuapp.com/)
* [timestamp repo](https://github.com/devNoiseConsulting/timestamp)
* [Request Header Parser Microservice](https://morning-headland-13993.herokuapp.com/)
* [Request Header Parser repo](https://github.com/devNoiseConsulting/Request-Header-Parser)

### Day 57: March 3, 2017

**Today's Progress:** Worked on another daily programmer challenged from the Phillydev slack. Trying to find best price per square foot from a csv file.

**Thoughts:** Letting people know that parsing csv is evil. Luckily the data was clean and simple. Wrote a lot of functions for filter and reduce. Would be nice if I could bind some variables to the functions. If I knew how to do that, then I could reduce the number of functions I wrote.

**Link to work:**
* [Best price per square foot Gist](https://gist.github.com/devNoiseConsulting/2d6737aa0a2f7411794e04d9e6916355)

### Day 58: March 4, 2017

**Today's Progress:** Started work on freeCodeCamp's URL Shortener Microservice.

**Thoughts:** Signed up with mLab for the projects storage portion. Verification email took a while to reach my inbox. Will work some more on it tomorrow. Get the repo setup and stubbed out the three routes that the microservice will have.

**Link to work:**
* [URL Shortener repo](https://github.com/devNoiseConsulting/URL-Shortener)

### Day 59: March 5, 2017

**Today's Progress:** Finished working on freeCodeCamp's URL Shortener Microservice and deployed to Heroku.

**Thoughts:** Got the MongoDB setup on mLab. Searched for examples of how integrate MongoDB into an express app. Getting the app deployed to Heroku is getting easier, though I did forget to setup the env variables before testing the app.

**Link to work:**
* [freeCodeCamp Profile](https://www.freecodecamp.com/devnoiseconsulting)
* [URL Shortener microservice](https://protected-dawn-47162.herokuapp.com/)
* [URL Shortener repo](https://github.com/devNoiseConsulting/URL-Shortener)

### Day 60: March 6, 2017

**Today's Progress:** Started working on freeCodeCamp's Image Search Abstraction Layer project and deployment to Heroku.

**Thoughts:** Spent a lot of time trying to figure which search api to use for this project. Going with Google Custom Search Engine after reading some posts on the freeCodeCamp forum. The rest of the work was just basic project/repo setup.

**Link to work:**
* [Image Search Abstraction Layer](https://vast-sea-39536.herokuapp.com/)
* [Image Search Abstraction Layer repo](https://github.com/devNoiseConsulting/Image-Search-Abstraction-Layer)

### Day 61: March 7, 2017

**Today's Progress:** Finished and deployed freeCodeCamp's Image Search Abstraction Layer.

**Thoughts:** With all the bits setup yesterday, today really focused on getting the code written. Reused a bit of code from the URL Shortener to get the mondoDB going. Since the Google Custom Search Engine API call used HTTPS we needed to require('https').

**Link to work:**
* [freeCodeCamp Profile](https://www.freecodecamp.com/devnoiseconsulting)
* [Image Search Abstraction Layer](https://vast-sea-39536.herokuapp.com/)
* [Image Search Abstraction Layer repo](https://github.com/devNoiseConsulting/Image-Search-Abstraction-Layer)

### Day 62: March 8, 2017

**Today's Progress:** With the completion of the File Metadata Microservice, I've finished all of freeCodeCamp's API Projects.

**Thoughts:** Grinding through these projects. Other than figuring out how to handle the file upload, this was an easy project to work on. Was going to make the static index page fancy with some BootStrap v4, but ditched it. Ran into content placement issues with a navbar. Also, I've run out of free apps on Heroku and had to add a credit card to be able to add more apps to the free dynos.

**Link to work:**
* [freeCodeCamp Profile](https://www.freecodecamp.com/devnoiseconsulting)
* [File Metadata Microservice](https://pacific-wave-24494.herokuapp.com/)
* [File Metadata Microservice repo](https://github.com/devNoiseConsulting/File-Metadata-Microservice)

### Day 63: March 9, 2017

**Today's Progress:** Worked on a daily programming challenge from the PhillyDev Slack.

**Thoughts:** The Zig Zag sequence is a tough problem. Came up a solution that solved all but one of the test sequences. Ported a java solution to javascript and made some optimizations.

**Link to work:**
* [Longest Zig Zag Gist](https://gist.github.com/devNoiseConsulting/e93f666c87f49dbfc2f09c24d5426f6d)

### Day 64: March 10, 2017

**Today's Progress:** Setting up a Woo Commerce site. Worked on a daily programming challenge from the PhillyDev Slack.

**Thoughts:** Daily programming challenge was pretty straight forward today. Trying to learn some WordPress and Woo Commerce.

**Link to work:**
* [Brickyard Weapons](https://brickyardweapons.flynnmj.org/)
* [Reverse Factorial Gist](https://gist.github.com/devNoiseConsulting/f6b3b4bfba55d1275ab65f226542b26b)

### Day 65: March 11, 2017

**Today's Progress:** Build the markdown previewer, unfortunately didn't use React.

**Thoughts:** Thought I'd drop back to the Data Visualization tasks. Unfortunately, they have a lot of coming soon sections. Still need a decent introduction to React before I can start using it. Dropped back to just using Vanillia JavaScript to complete the challenge. Not marking it done on freeCodeCamp.

**Link to work:**
* [Markdown Previewer](http://codepen.io/_dev_noise/pen/xqdWOq)

### Day 66: March 12, 2017

**Today's Progress:** Learning some ReactJS at Codecademy and got 2 badges.

**Thoughts:** Starting to look into ReactJS. Moved over to Codecademy since freeCodeCamp is still working on a ReactJS challenges.

**Link to work:**
* [codecademy Achievements](https://www.codecademy.com/users/flynnmj/achievements)

### Day 67: March 13, 2017

**Today's Progress:** Learning some ReactJS at Codecademy and got 3 badges.

**Thoughts:** Continuing with learning react. I get how it works, but it is a but strange to put html in my JavaScript. Tend to prefer the Angular way and just put bindings on my HTML to hook into my Javascript.

**Link to work:**
* [codecademy Achievements](https://www.codecademy.com/users/flynnmj/achievements)

### Day 68: March 14, 2017

**Today's Progress:** Completed Learn ReactJS: Part I at Codecademy and got 3 badges.

**Thoughts:** More hands on work with ReactJS. Really need a shortcut for document.getElementById().

**Link to work:**
* [codecademy Achievements](https://www.codecademy.com/users/flynnmj/achievements)

### Day 69: March 15, 2017

**Today's Progress:** Started Learn ReactJS: Part II at Codecademy and got 3 badges. Worked on a daily programming challenge from the PhillyDev Slack.

**Thoughts:** Reviewing concepts learned in Part II, but also applying React design patterns. The Combinatorial Sum was tricky to start and my initial attempt was scrapped. Though in both attempts I went for a brute force method to generate all the combinations.

**Link to work:**
* [codecademy Achievements](https://www.codecademy.com/users/flynnmj/achievements)
* [Finding Combinatorial Sums Gist](https://gist.github.com/devNoiseConsulting/9efde9d55cca8e99e80242bca9ed7366)

### Day 70: March 16, 2017

**Today's Progress:** More Learn ReactJS: Part II at Codecademy and got 4 badges. Worked on a daily programming challenge from the PhillyDev Slack.

**Thoughts:** More React concepts. Generally try to keep the components simple. Make display component stateless and move logic to a parent component.

**Link to work:**
* [codecademy Achievements](https://www.codecademy.com/users/flynnmj/achievements)
* [Sort With Old Position](https://gist.github.com/devNoiseConsulting/d3eb37268dc76dbca5fd1491b362b884)

### Day 71: March 17, 2017

**Today's Progress:** Finished Learn ReactJS: Part II at Codecademy and got 3 badges. Worked on a daily programming challenge from the PhillyDev Slack.

**Thoughts:** The life cycle calls the covered make sense, but I think I'll understand them better when I have code that uses them. Did FizzBuzz for the daily programming challenge. Was pretty straight forward so I made a couple of solutions. Turns out that .map and .forEach seem to be faster then a for loop.

**Link to work:**
* [codecademy Achievements](https://www.codecademy.com/users/flynnmj/achievements)
* [FizzBuzz](https://gist.github.com/devNoiseConsulting/97e264fcf71058c1e8514a0325707000)

### Day 72: March 18, 2017

**Today's Progress:** Worked on a React version of the Markdown Previewer for freeCodeCamp.

**Thoughts:** Converting code from a Codecademy exercise for this challenge. I thought I had working code, but can't get it to work on CodePen. Keep getting a "Unclosed Regular Expression". I thought the Babel transpiler would take care of this.

**Link to work:**
* [CodePen](http://codepen.io/_dev_noise/pen/jBYYKR)

### Day 73: March 19, 2017

**Today's Progress:** More work on a React version of the Markdown Previewer for freeCodeCamp.

**Thoughts:** Followed Codecademy's articles on setting a React dev. Since I already have Node.js installed, it was mostly getting the project setup and installing the npm modules.
Other than one problem with the JSX, the code I had written worked. Bigger problem is that I can get BootStrap into the app via Webpack.

**Link to work:**
* [Markdown Previewer Repo](https://github.com/devNoiseConsulting/Markdown-Previewer)

### Day 74: March 20, 2017

**Today's Progress:** Completed the Markdown Previewer challenge for freeCodeCamp. Also did a Cardinality Sort for the daily programming challenge from the PhillyDev Slack.

**Thoughts:** Went back to CodePen as that is the only way to complete the challenge. Drop back a bit and implement one component at a time. I think the HTML I used in the App component might have the root cause of my initial problems. Also Taking JSX HTML and putting it in HTML might cause a problem since className won't apply a CSS class to the element.

**Link to work:**
* [freeCodeCamp Profile](https://www.freecodecamp.com/devnoiseconsulting)
* [CodePen](http://codepen.io/_dev_noise/pen/jBYYKR)
* [Cardinality Sort Gist](https://gist.github.com/devNoiseConsulting/df2b6d92b9aef0ff52b87ec89c4a040f)

### Day 75: March 21, 2017

**Today's Progress:** Started working on the Camper Leaderboard challenge for freeCodeCamp. Also did a digit sum for the daily programming challenge from the PhillyDev Slack.

**Thoughts:** Figured how to make React generate multiple components. Made use of componentDidMount to make the initial fetch for the data. Didn't have enough time to figure out getting webpack to process CSS files.

**Link to work:**
* [Camper Leaderboard Repo](https://github.com/devNoiseConsulting/Camper-Leaderboard)
* [Digit Sum Gist](https://gist.github.com/devNoiseConsulting/e67f546adad4b5ee5ea9e2b279f56c85)

### Day 76: March 22, 2017

**Today's Progress:** Completed working on the Camper Leaderboard challenge for freeCodeCamp. Also did a weighted digit sum for the daily programming challenge from the PhillyDev Slack.

**Thoughts:** I may need to look into sass some more, but I tend to stick with Bootstrap for styling my UI. I've taken to making github repos for the challenges/projects as I get better feedback than Codepen gives me. Spent a lot of time trying to get webpack to suck in Bootstrap. Will need to look into webpack to figure a good build process.

**Link to work:**
* [freeCodeCamp Profile](https://www.freecodecamp.com/devnoiseconsulting)
* [CodePen](https://codepen.io/_dev_noise/pen/BWrXgY)
* [Camper Leaderboard Repo](https://github.com/devNoiseConsulting/Camper-Leaderboard)
* [Weighted Sum of Digits Gist](https://gist.github.com/devNoiseConsulting/26947e4496308a3e48865c74c5502b68)

### Day 77: March 23, 2017

**Today's Progress:** Started working on the Game of Life project for freeCodeCamp.

**Thoughts:** Getting the repo setup, loading the needed npm modules, and setting up the initial components. Making the child components as stateless as possible, so I need to send a lot of props down. Next step is to figure out how to send a click up the components to indicate that the user has populated a cell.

**Link to work:**
* [Game of Life Repo](https://github.com/devNoiseConsulting/Game-of-Life)

### Day 78: March 24, 2017

**Today's Progress:** Daily programming challenges from the PhillyDev Slack.

**Thoughts:** The Vowel Count was pretty easy after the Word Ladder problem from Thursday. The conversation about my Word Ladder solution got me to work on some revisions to improve the weighting for changing words.

**Link to work:**
* [Vowel Count Gist](https://gist.github.com/devNoiseConsulting/074de986f1679fa6d88daa1f7be2c00c)
* [Word Ladder Gist](https://gist.github.com/devNoiseConsulting/a2c8fb0223f45b3f1b7b2db7b34db631)

### Day 79: March 25, 2017

**Today's Progress:** Working on the Game of Life project for freeCodeCamp.

**Thoughts:** Worked on getting the code to pass the toggleCell down the component chain so the table cell could handle the click correctly. The worked on the functions for the buttons to work with. Then spent a lot of time figuring out code for the next generation.

**Link to work:**
* [Game of Life Repo](https://github.com/devNoiseConsulting/Game-of-Life)


### Day 0: February 30, 2016 (Example 1)
##### (delete me or comment me out)

**Today's Progress**: Fixed CSS, worked on canvas functionality for the app.

**Thoughts:** I really struggled with CSS, but, overall, I feel like I am slowly getting better at it. Canvas is still new for me, but I managed to figure out some basic functionality.

**Link to work:** [Calculator App](http://www.example.com)
