---
title: 'My Frontend Development Strategy'
date: '2022-12-01'
---

## Frontend Development Estrategy

In general, frontend development is made of **Structure, Stylization and Functionalities**. Among many frameworks and libs there exists this basic structure is the same because it is pretty conected to the Web Basis of HTML (Structure), CSS (Stylization) and JavaScript (Funcionalities).

### Development Proccess

I like to develop using this steps one after the other. First thing I do is to build the page structure with HTML, JSX or whetever i`m using at the moment. In this part I only care about create a greate foundatio, very clear and easy to understand and with the proper rules 

**Creating the Structure**

  - Translate the design into the page skeleton
  - Use self explanatory tags like:
    - div
    - section
    - span
    - h1, h2, h3
    - footer
    - p
    - a
    - button
  - Follow the design build the page from top to bottom

A lot of people with whom I worked had a lot of difficult styling pages. CSS or any stylization tool/technologie that you use needs practice. You need to put yourself in challenging situations where you need to think and use your creative to create the styles that you need.

**Creating the Stylization**

  - Most important concepts for me:
    - Position:
      - Absolute, Fixed and Regular
    - Display: 
      - Block, Flex and Grid
  - Where to practice: 
    - [Flexbox Froggy](https://flexboxfroggy.com/)
    - [CSS Speedrun](https://css-speedrun.netlify.app/)
    - [Guess CSS](https://www.guess-css.app/)
  
Lastly I give life to the screen. Just like the proccess of hydratation that happens when applications rendered the HTML in the browser and after that make the hydratation with JavaScript is the proccess that i like to follow. At the beginning I usually use mock values (hard coded values) because I just thinking about the structure and style. Only in the last step I create the conections with APIs, functions, data collection or any other functionality that my page has and if needed (is always good) after all I look at the code and make all the restructurings and modularization necessary.

**Creating the Functionalities**

  - Restructurings and Modularization
    - Add typing (if possible).
    - Create components
        - If the code is used in other places
        - If the code is isolated from the screen
    - Search Bad Smells
        - Repeated Code
        - Large chain of IF and ELSE
        - Overengineering
        - Bloaters
        - Change Preventers
    - Make your code clean
        - Keep it Simple and Small (Keep it Simple Stupid)
        - Indentation
        - Few comments (only if needed)
            - If your code don`t explain himself, something is wrong
        - Don`t use magical numbers
        - Use great names for variables and functions 