## Website Performance Optimization portfolio project
This is the page for my final project for the class [Critical Rendering Path course](https://www.udacity.com/course/ud884), which is part of the Front-end Web Developer Nanodegree. The original files can be found [here](https://github.com/udacity/frontend-nanodegree-mobile-portfolio). The changes presented on this document are related to the subpage "/views/pizza.html".

## PageSpeed
[Link](https://developers.google.com/speed/pagespeed/insights/?url=http%3A%2F%2Flucasdf.github.io%2Foptimization-project%2Fviews%2Fpizza.html)
Mobile: 96/100 Speed
Desktop: 95/100

## Resources
http://cssminifier.com/
http://javascript-minifier.com/
https://tinypng.com/

## Changelog
CSS - stylesheet.css
1. The two original CSS files were merged into one, reducing the number of downloads needed.
2. The CSS file was minified (stylesheet-min.css).
3. The CSS loading tag was moved to the end of the HTML file.

JavaScript - main.js
1. Added a "template" variable to be used with the ".cloneNode()" function. I noted a slight improvement on the performance (time to load the page) using this approach. (Lines 362 and 542).
2. The loop inside "function changePizzaSizes" was optimized (Line 455).
3. The loop responsible for appending the sliding pizzas was optimized (Line 478).
4. The loop inside "function updatePositions()" was optimized (Line 515).
5. The loop responsible for generate the sliding pizzas was optimized (Line 557).
6. The number of sliding pizzas to be generate was adjusted according to the screen size of the user, avoiding the creation of sliding pizzas that would never be displayed (Line 555).
7. A few changes on the performance.mark (Lines 501, 532 and 550).

Images - pizzeria.jpg and pizza.png
1. Both files were compressed, achieving a great reduction on the size. The file "pizzeria.jpg" changed from 2370kb to 32kb, and the file "pizza.png" changed from 49kb to 10kb.

## Notes
1. I was unable to achieve a score higher than 87 for Mobile without moving the CSS to be loaded on the end of HTML file. This is not the optimal solution because it may cause a Flash of Unstyled Content (FOUC). The other solutions to achieve a higher score without doing so could be to inline portions of the CSS, which I don't particularly like, and set appropriate cache of the resources, which I am unable to do while using Githut Pages.
2. I could have optimized the CSS more if I had removed unnecessary classes from the file.
