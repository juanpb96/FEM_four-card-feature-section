# Frontend Mentor - Four card feature section solution

This is a solution to the [Four card feature section challenge on Frontend Mentor](https://www.frontendmentor.io/challenges/four-card-feature-section-weK1eFYK). Frontend Mentor challenges help you improve your coding skills by building realistic projects! 

## Table of contents

- [Overview](#overview)
  - [The challenge](#the-challenge)
  - [Screenshot](#screenshot)
  - [Links](#links)
- [My process](#my-process)
  - [Built with](#built-with)
  - [What I learned](#what-i-learned)
  - [Continued development](#continued-development)
  - [Useful resources](#useful-resources)
- [Author](#author)

## Overview

### The challenge

Users should be able to:

- View the optimal layout for the site depending on their device's screen size

### Screenshot

Desktop view:

![Solution preview](./design/Screenshot_preview-Four-card-feature-section.png)

### Links

- Solution URL: [Click here](https://www.frontendmentor.io/solutions/mobile-first-site-html-scss-grid-and-flexbox-zQd4ZSrd7)
- Live Site URL: [See live site here](https://juanbonilla.me/FEM_four-card-feature-section/)

## My process

### Built with

- Semantic HTML5 markup
- SCSS / CSS custom properties and functions
- Flexbox
- CSS Grid
- Mobile-first workflow

### What I learned

I learned to use sass custom functions to avoid specifying more class selectors for every card in my HTML, and make a solution with the ```:nth-child``` pseudo-class to select each card individually. In this case, I decided to look for a way of implement an array to encapsulate my color variables and with a for loop iterate that array in order to include a top border for each card with different color. See below what I did:

```scss
.card {
    // Card general styles...

    @for $i from 1 through 4 {
        &:nth-child(#{$i}) {
            // Create a new element inside every card
            &::before {
                content: "";
                position: absolute;
                width: 100%;
                top: -4px;
                left: -4px;
                // Use a variable that contains a list of colors and select the specific color for each card
                border: 4px solid nth($card-border-colors, $i); 
            }
        }
    }
}
```

### Continued development

In this project I found how useful was to use functions and specific characteristics that SASS has. With this solution I understood the benefit of avoid writting repetitive styles for similar class selectors and that helped me accomplish this solution in a short time period.

### Useful resources

- [Using lists in SASS](https://sass-lang.com/documentation/values/lists) - This helped me when I wanted to encapsulate some values in an array-like expression.
- [Using for loop in SASS](https://sass-lang.com/documentation/at-rules/control/for) - This helped me when I was thinking in a solution to avoid writting repetite code in my styles combining a for loop with lists.

**Note: Delete this note and replace the list above with resources that helped you during the challenge. These could come in handy for anyone viewing your solution or for yourself when you look back on this project in the future.**

## Author

- Website - [juanbonilla.me](https://juanbonilla.me)
- Frontend Mentor - [@juanpb96](https://www.frontendmentor.io/profile/juanpb96)
- LinkedIn - [Juan Bonilla](https://www.twitter.com/yourusername)
