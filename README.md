# Frontend Mentor - Results summary component solution

This is a solution to the [Results summary component challenge on Frontend Mentor](https://www.frontendmentor.io/challenges/results-summary-component-CE_K6s0maV). Frontend Mentor challenges help you improve your coding skills by building realistic projects. 

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
- [Installation](#installation)


## Overview

### The challenge

Users should be able to:

- View the optimal layout for the interface depending on their device's screen size
- See hover and focus states for all interactive elements on the page

### Screenshot
#### Desktop
<img src="https://github.com/ivanwritescode/results-summary-component/blob/master/screenshots/desktop-1440px.png" alt="Desktop Screenshot" width="600" />

#### Mobile
<img src="https://github.com/ivanwritescode/results-summary-component/blob/master/screenshots/mobile-375px.png" alt="Mobile Screenshot" width="300" />

### Links

- GitHub URL: [Code URL](https://github.com/ivanwritescode/results-summary-component)
- Solution URL: [Solution URL](https://www.frontendmentor.io/solutions/responsive-design-using-sass-zhVByyH5Lx)
- Live Site URL: [Live Site](https://ivanwritescode.github.io/results-summary-component/)

## My process
In this project, I've wanted to get back to basics and improve my HTML and CSS skills while I'm also learning React at the same time. I have used SASS to help organize my CSS code better and learned a lot about it in the process as well.

### Built with

- Semantic HTML5 markup
- SASS/SCSS preprocessor 
- Flexbox
- Custom fonts
- Mobile-first workflow
- [React](https://reactjs.org/) - JS library

### What I learned
1. Referencing fonts using `@font-face` directive on SCSS file. Also the best practices of importing/using fonts in the project (i.e. `font-display: swap` and `format('truetype')`).
```scss
@font-face {
    font-family: 'HankenGrotesk';
    font-display: swap;
    font-weight: 100 900;
    src: url(../../../assets/ResultsSummary/fonts/HankenGrotesk-VariableFont_wght.ttf)
        format('truetype')
}
```
2. The usage of variables on SCSS for colors and gradients.
3. The usage of maps.
4. How to use `@each` directive. I have utilized the directive to apply the color values from my SCSS map in order to style each individual list item within the component.

```scss
/* accents */
$accents: (
  accent-0: (hsl(0, 100%, 67%), hsl(0, 100%, 67%, .1)),
  accent-1: (hsl(39, 100%, 56%), hsl(39, 100%, 56%, .1)),
  accent-2: (hsl(166, 100%, 37%), hsl(166, 100%, 37%, .1)),
  accent-3: (hsl(234, 85%, 45%), hsl(234, 85%, 45%, .1))
);
---

@each $accent, $colors in $accents {
    $background: nth($colors, 2);
    $color: nth($colors, 1);

    li[data-item-type=#{$accent}] {
        background: $background;

        span {
        color: $color;
        }
    }
}
```
5. Got more experience in SCSS nesting and code organization.
6. How to use !important declaration to override cascading behavior sparingly. Only to be used as a last resort.
7. The difference between em and rem for font sizes, paddings, and margins.
8. Usage of hsl and hsla
9. How to use custom data or data-* attributes to pinpoint specific elements. Here I've used js map() method on my data object and used the index for each data item.
```tsx
    <li key={d.category} data-item-type={`accent-${i}`}>
```
10. How to structure code properly and proper use of sematic elements in HTML
11. Better understanding of flexbox, justify-content, and align-items properties
12. Difference between `<b>`, `<strong>`, and `<em>`
13. How to choose breakpoints properly.
14. How to not add unnecessary media quries for mobile if your approach is already mobile-first.
15. To not style on IDs or use complex CSS selectors.
16. Media queries should always be defined in rem or em.
17. To know the difference between using `<main>` and `<header>` tags.
18. To never leave text in a div/span alone and to always use meaningful elements like paragraph or heading tags.
19. That putting `<button>` inside a paragraph tag is an invalid HTML.
20. The dangers of using `em` on font sizes.
21.  To makes sure to always include moder CSS reset at the very start of the styles so that the styling is consistent accross browsers.
22. That it's more performant to load fonts in the HTML head than rely on CSS import.
23. To always make sure to use `role="list"` in ul and `role="listitem"` in each li when list style is removed in CSS.
24. To always consider adding a little defensive styling such as `flex-wrap: wrap` to make sure items like text wraps properly on small screen devices.

### Continued development

- In my future solutions, I want to use more SASS features to get comfortable with the capabilities SASS can bring to my development kit. I want to get to know more about directives, mixins, modules, and more!
- Throughout the process of making this solution, the usage of custom CSS properties also came to my attention and want to get familiar with it as well.
- I want to understand more about standard HTML practices such as accessibility, proper usage of sematic tags, aria properties, and proper structuring of my HTML documents to maximize accessibility and SEO.

### Useful resources

- [Planning HTML](https://fedmentor.dev/posts/html-plan-product-preview/) - This helped me understand HTML structure a little bit more. I really liked this pattern and will use it going forward.
- [HTML Sectioning](https://css-tricks.com/how-to-section-your-html/) - This is an amazing article which helped me finally understand sectioning HTML elements. I would like to use this as a reference my future projects. 
- [SASS Maps](https://sass-lang.com/documentation/values/maps) - This documentation page helped me understand SASS maps.

## Author

- Website - [portfolio](https://ivanwritescode.github.io/my-portfolio/)
- Frontend Mentor - [@ivanwritescode](https://www.frontendmentor.io/profile/ivanwritescode)
- Twitter - [@ivanwritescode](https://twitter.com/ivanwritescode)

## Installation

Follow these steps to install and run the project locally:

```bash
# Clone the repository
git clone https://github.com/ivanwritescode/results-summary-component.git

# Navigate to the project directory
cd frontendmentor-solutions 

# Install the dependencies
npm install

# Start the development server
npm run dev