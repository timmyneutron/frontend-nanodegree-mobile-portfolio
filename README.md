# Udacity Front-End Nanodegree Project #3: Mobile Portfolio (Performance Optimization)

The task for this project was to take an existing project ([forked from here](https://github.com/udacity/frontend-nanodegree-mobile-portfolio)) and optimize it for download speed and smooth animation.

Source code is in the src folder. Production code, which includes a minified version of index.html, is in the dist folder.

## Getting Started
To serve the website, clone the directory, navigate to the dist folder, and run a local server
```sh
$> cd /path/to/your-project-folder
$> python -m SimpleHTTPServer 8080
```
Then run [ngrok](https://ngrok.com/) to make the page remotely accesible
```sh
$> ./ngrok http 8080
```
Copy/paste the provided url into your browser to access the site remotely.
## Testing Download Speed
The homepage will show the times to load and complete building the DOM in the lower right hand corner
## Testing Animation
Click the "Cam's Pizzeria" link to navigate to the randomly generated pizzeria. Scroll up and down to test for smooth animation of the background pizzas. Adjust the size slider to change the size of the randomly generated pizzas.
