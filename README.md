# Udacity Front-End Nanodegree Project #3: Mobile Portfolio (Performance Optimization)

The task for this project was to take an existing project ([forked from here](https://github.com/udacity/frontend-nanodegree-mobile-portfolio)) and optimize it for download speed and smooth animation.

Source code is in the src folder. Production code, which includes a minified version of index.html, is in the dist folder.

## Getting Started
To serve the website, clone the directory, navigate to the dist folder, and run a local server
```sh
$> cd /path/to/your-project-folder
$> python -m SimpleHTTPServer 8080
```
Then download [ngrok](https://ngrok.com/) to the dist folder and run it to make the page remotely accesible
```sh
$> ./ngrok http 8080
```
Copy/paste the provided url into your browser to access the site remotely.
## Testing Download Speed
The homepage will show the times to load and complete building the DOM in the lower right hand corner
## Testing Animation
Click the "Cam's Pizzeria" link to navigate to the randomly generated pizzeria. Scroll up and down to test for smooth animation of the background pizzas. Adjust the size slider to change the size of the randomly generated pizzas. The console prints out the time it takes to animate 10 frames of the background pizzas, and the time it takes to change the size of the randomly-generated pizzas.
## Optimizations
##### The following changes were made to index.html optimize download speed:
1. I shrunk the size of views/images/pizzeria.jpg to fit the size it appears as in the page
2. I inlined style.css (which is render-blocking) into index.html (lines 13 - 83)
3. I added a print media query to the print.css link in index.html (line 10)
4. I downloaded the Open Sans webfont from Google Fonts, and referenced the webfont files in the inlined css in index.html (lines 64 - 82)
5. I minified index.html for the production version (in the dist folder)

##### The following changes were made to views/js/main.js to optimize animation for views/pizza.html:
1. I used a switch statement to set the width of the randomly-generated pizzas, and then applied that width using a for loop and the style.width property (lines 427 - 450)
2. I changed all references to document.querySelector() to document.getElementById() or document.getElementByClassName()
3. I calculated the number of background pizzas needed based on screen height, to avoid rendering an unnecessarily large number of background pizzas (line 536)
4. I used the style.transform property to translate the pizzas and to avoid layout thrashing (line 508)
5. I used requestAnimationFrame() to run updatePositions() for the background pizzas at the beginning of each animation frame (lines 524 - 526)
