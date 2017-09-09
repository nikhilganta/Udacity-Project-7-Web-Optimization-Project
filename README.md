# Udacity Project - Web Optimization

## Introduction
In this project, a portfolio was given and two tasks were given to complete
- PageSpeed Insight Score of the index.html should be atleast 90 for Mobile and Desktop.
- Optimizations made to views/js/main.js make views/pizza.html render with a consistent frame-rate at 60fps when scrolling.

## Run the Website
- Here is the [link](https://cdn.rawgit.com/nikhilganta/Udacity-Project-7-Web-Optimization-Project/43e31648/index.html) to the portfolio site.
- Click on Cam's Pizzeria to visit the pizza site and other links which will take you to their detailed work.

## Optimizations Performed
### Part 1: PageSpeed Insight should be atleast 90
- The inlining of the style.css file in the index.html.
- Adding a media = "print" attribute to the print.css link in the index.html which avoids render blocking.
- Adding an async attribute to the script analytics.js to avoid parser blocking.
- The images were given restrictions on width and height which compress them to the required memory.
- The pizzeria.jpg file which was around 2.4 MB was compressed to around 34 KB since the thumbnail on the main page did not require that high quality of image.

### Part 2: Optimization to make pizza.html perform at 60fps
- Two new variables are assigned to avoid repition of the same commands.
  - var randomPizzaLength = document.querySelectorAll(".randomPizzaContainer").length; and
  - var randomPizza = document.querySelectorAll(".randomPizzaContainer");
- In the changePizzaSizes function, an additional loop was created for setting the element's width (style.width). This was done to avoid recalculate and run layout everytime in the loop instead all the style elements and layout elements were grouped in different loops so that they run at a time continously and avoid Forced synchronous layout.
- var pizzasDiv is taken out of the loop to avoid forced synchronous layout.
- Changed the number of pizzas to be displayed based on the browser's inner dimensions.
