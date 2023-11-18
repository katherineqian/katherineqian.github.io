---
title: "Skinbytes"
date: 2020-06-01
cover:
  image: "/early-glowdex/cover.png"
#tags: []
---
#### Glowdex v0.
### What it is
I developed a full-stack web app with a Python/Flask RESTful API, a MySQL DB backend, and Bootstrap/JavaScript/React frontend. I hosted it on PythonAnywhere and beta tested it with about 35 Reddit skincare community users.

**Fun fact**: I demoed this for Stephanie Simon when I interviewed for YC with this and she said it was "slick". Pretty exciting for me early in my dev/founder journey.

### The concept
A single skincare product has reviews and other information about it distributed across the internet. The idea for this was to automatically compile them into one place, which would be your one-stop-shop for skincare research.

![name](/early-glowdex/reviews-landing.png#center)

I used Selenium/Python for webscraping. I also created and designed the MySQL DB and schemas for this project, which maintained about 180K records for popular skincare products.

### Features
A selection of features I’m proud of include:

#### Compilation of reviews across different sites
This was the point of the whole app. I generated a summary graph that allowed you to see how star ratings compared across different sites. Try taking a guess at which sites tended to have higher reviews :-)
![Product page](/early-glowdex/reviews-2.png#center)
![Reviews example](/early-glowdex/reviews-4.png#center)

#### Ingredients comparison tool
I also made a comparison tool where you could select up to 5 products from my db and it would show what's in common. Pretty useful for comparing similar formulations.

![Ingredients comparison](/early-glowdex/reviews-7.png#center)

#### Ingredients highlighting
We researched ingredients known to be helpful and harmful (irritating, sensitizing, or allergenic) to skin, then automatically highlighted those on the product page.

![Ingredients highlighting](/early-glowdex/reviews-3.png#center)

#### Integration of Reddit and YouTube APIs
I always check Reddit and YouTube when researching my next skincare product, and I tend to use the same search string each time. I automatically did this for the user on the product page.

![Youtube API](/early-glowdex/reviews-5.png#center)
![Youtube API](/early-glowdex/reviews-6.png#center)
