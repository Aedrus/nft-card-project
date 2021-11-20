# Frontend Mentor - NFT preview card component solution

This is a solution to the [NFT preview card component challenge on Frontend Mentor](https://www.frontendmentor.io/challenges/nft-preview-card-component-SbdUL_w0U). Frontend Mentor challenges help you improve your coding skills by building realistic projects. 

## Table of contents

- [Overview](#overview)
  - [The challenge](#the-challenge)
  - [Screenshot](#screenshot)
- [My process](#my-process)
  - [Built with](#built-with)
  - [What I learned](#what-i-learned)
  - [Continued development](#continued-development)
- [Author](#author)

## Overview

### The challenge

Users should be able to:

- View the optimal layout depending on their device's screen size
- See hover states for interactive elements

### Screenshot

![](./assets/images/solution-screenshot.png)

Add a screenshot of your solution. The easiest way to do this is to use Firefox to view your project, right-click the page and select "Take a Screenshot". You can choose either a full-height screenshot or a cropped one based on how long the page is. If it's very long, it might be best to crop it.
Then crop/optimize/edit your image however you like, add it to your project, and update the file path in the image above.

## My process

### Built with

- HTML5
- CSS
- SASS (SCSS)
- Flexbox
- Mobile-first workflow

### What I learned

Completing this project allowed me to practice using HTML and CSS/SASS, as well as my ability to problem solve and research. The latter being a skill that is very useful in Web Development.
I was pleasently suprised to discover that I've improved in my ability to understand how HTML and CSS work together to create functional and responsive components, such as this card. I now feel confident that I can reach new heights and move on to more complex projects.

Another thing I learned was how to use the psuedo selectors ::before and ::after to inject content on to the page without using html.
I used these selectors along with the :hover psuedo selector to create the hover effect on the card image.

First, I created a div with the class of card-image and then placed a div within with the class of card-image-main — this is styled to have the background image of the cube, among other properties.

```html
<div class="card-image flex flex-jc-c">
    <div class="card-image-main"></div>
</div>
```
```css
.card-image {
  border-radius: inherit;
  margin-bottom: 30px;
  position: relative;
}

.card-image-main {
  z-index: 1;
  border-radius: inherit;
  background: #000 url(/assets/images/image-equilibrium.jpg);
  background-position: center;
  background-color: $cyan;
  background-size: cover;
  width: 100%;
  height: 340px;
}
```

I then used the ::before selector to inject a cyan background with a default opacity of 0 to hide it and then, using :before:hover, I set the opacity to 0.5 to create the active state.
Very few anchor tags were used in this project as they were not needed, but for a real project we would need to anchor tags in place of certain elements.
```css
// Adds cyan overlay
.card-image::before {
  content: "";
  border-radius: inherit;
  position: absolute;
  background: $cyan;
  right: 0;
  left: 0;
  display: block;
  width: 100%;
  height: 100%;
  z-index: 2;
  opacity: 0;
}
// Reveals cyan overlay with a transition
.card-image:hover::before {
  opacity: 0.5;
  transition: 0.2s ease-in-out;
}
```

I then used the ::after selector to add the eye icon.
```css
.card-image::after{
  z-index: 2;
  position: absolute;
  top: 42%;
  bottom: 0;
  content: url(/assets/images/icon-view.svg);
  opacity: 0;
}
.card-image:hover:after{
  opacity: 1;
  transition: 0.2s ease-in-out;
}
```
There were a few little things here and there but the most important aspect of this small project was practicing my skills and putting my knowledge to the test. Being able to research and understand new methods and practices of creating webpages allows for you to solve almost any problem.

### Continued development

I would love to understand JavaScript more as I find it has a large array (pun intended) of applications in web development and i'm still trying to gain a familiarty with it.
I also hope to create more complex media queries and breakpoints.

## Author

- Website - [Mario Ferrera](https://www.theardentauthor.com)
- Frontend Mentor - [@aedrus](https://www.frontendmentor.io/profile/yourusername)

