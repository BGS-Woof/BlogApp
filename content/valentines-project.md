+++ 
title = 'Simple Valentine’s Day Project with JS' 
date = 2023-11-22T16:55:24+01:00 
draft = false 
description = "Valentine’s Day Project." 
image = "/images/valentines.svg" 
imageBig = "/images/valentineb.svg" 
categories = ["js", "html", "css", "beginners"] 
authors = ["Samir Rahmatulaev"] 
avatar = "/images/avatar.jpeg" 
+++

## Introduction

This JavaScript project is an interactive application where users can interact with "Yes" and "No" buttons to change the displayed image. When the user clicks the "Yes" button, the image switches to another one, and similarly, clicking the "No" button triggers a change in the displayed image. Each time the user performs an action, the displayed image changes, creating an engaging and visually appealing experience.

## HTML Code

Let's build a structure of our project with HTML.

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Will you be my valentine?</title>
    <link rel="shortcut icon" href="heart-fill.svg" type="image/x-icon" />
    <link rel="stylesheet" href="style.css" />
  </head>
  <body>
    <div class="container">
      <div class="box">
        <img id="valentine-img" src="ask.gif" />
        <div class="content">
          <h2 id="valentine-text">Will you be my valentine?</h2>
          <p id="number"></p>
          <button class="acceptance" id="acceptance-btn">YES!</button>
          <button class="refuse" id="refuse-btn">NO!</button>
        </div>
      </div>
    </div>

    <script src="main.js"></script>
  </body>
</html>
```

## CSS Code

Let's add some styling with CSS.

```css
* {
  padding: 0;
  margin: 0;
  box-sizing: border-box;
  font-family: "Poppins", sans-serif;
}

#valentine-img {
  display: block;
  margin: auto;
  width: 300px;
}

.container {
  display: grid;
  place-items: center;
  height: 100vh;
}

.content {
  text-align: center;
}

h2 {
  color: #e75480;
  font-size: 36px;
  text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.5);
}

.acceptance,
.refuse {
  font-size: 24px;
  padding: 10px 20px;
  margin: 10px;
  border: none;
  border-radius: 20px;
  cursor: pointer;
  text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.5);
  transition: 0.6s;
}

.acceptance {
  background-color: #e75480;
  color: white;
}

.refuse {
  background-color: #5b5b5b;
  color: white;
}

.acceptance:hover {
  background-color: #d64571;
}

.refuse:hover {
  background-color: #494949;
}
```

## JS

Now let's make our project alive with JS.

```js
// Getting html elements
const valentine_img = document.getElementById("valentine-img");
const valentine_text = document.getElementById("valentine-text");
const acceptance_btn = document.getElementById("acceptance-btn");
const refuse_btn = document.getElementById("refuse-btn");
const num = document.getElementById("number");

// Array of images to be displayed on refusal
const images_refuse = ["sad.gif", "sad2.gif", "sad3.gif", "angry.gif"];

// Array of textual messages to be displayed on refusal
const text_refuse = [
  "Maybe you want to change your opinion?",
  "Maybe you can give a chance, please?",
  "Please I'm begging you with all my heart!",
  "You don't deserve me!",
];
let currentIndex = 0; // Index of the current image/text in the refusal arrays

// Event handler for the refusal button
refuse_btn.addEventListener("click", () => {
  // Check if we've reached the end of either the images or text arrays
  if (
    currentIndex === images_refuse.length ||
    currentIndex === text_refuse.length
  ) {
    refuse_btn.disabled = true; // If so, disable the refusal button
    return;
  }

  // Set new image and text on refusal
  valentine_img.src = images_refuse[currentIndex];
  valentine_text.textContent = text_refuse[currentIndex];
  num.textContent = ""; // Clear the phone number
  currentIndex++; // Increment index for the next image/text
});

// Event handler for the acceptance button
acceptance_btn.addEventListener("click", () => {
  // Set image and text on acceptance
  valentine_img.src = "love-happy.gif";
  valentine_text.textContent = "THANK YOU MY LOVE!";
  num.textContent = "Call me baby: +996552911166))"; // Provide the phone number
});
```

## Notification!
For this project you should add at least 6 images no less!

I think we can finish here, you can also view the source code of this project on my **[GitHub account](https://github.com/BGS-Woof/Valentine-Day-poll)**