---
title: What Is Front-end Development?
date: 2021-02-03
---

Front-end development is the literal front end of what we see on a website, the user interface. The user interface consists of...
* text
* buttons
* visual design (css)
The user uses the user interface to interact with the website.

Types of code used in Front-end Dev...
* HTML- for what to display
* css- for how to display it
* javascript- for how parts of the website interact with each other (buttons, etc..)

### My Experience With Front-end Development

<iframe src="https://011-frontend-development-pinboard-st8fromfarm.dbcs.repl.co/" width="900" height="450"></iframe> 

Over the course of the last few weeks I have built a pin board. This board can

* display pictures on the site with tags
* add new pictures with tags
* search for tags

The pin board has all three types of code in front-end development, it uses 

# HTML

The big HTML elements of the site are the header, this 

* Links other files to the index
* Links link to font
* displays what the name of the site is

This is the header to my pinboard

```header
<html>
  <head>
    <meta charset="utf-8" />
    <title>My Dogeboard</title>
    <link rel="stylesheet" href="style.css" />
    <link rel="preconnect" href="https://fonts.gstatic.com">
    <link href="https://fonts.googleapis.com/css2?family=Balsamiq
    +Sans:ital,wght@1,700&display=swap" rel="stylesheet">

  </head>
```

The next part of the HTML is the body, this is the rest of the index. The body does things like

* Defines things for js to work with
* Puts text on the site for css to work with

This is an part of the Body

```body
<div class="cardContainer" id="cardContainer"></div>
    <div id="newCardModal" class="modal">
      <div class="modal-content">
```

# css

css is the style of a site

* where text is
* what color the text and background and everything is
* how big or small anything is
* what font text is

Here is a section defining part of the HTML

```css
h1 {
  font-size: 4rem;
  text-align: center;
  font-family: 'Balsamiq Sans', cursive;
  color: #e9b303;
  text-shadow: 0 0 5px #dba902;
}
```

# Javascript

Javascript is the last coding language that Front-end devs use. It does many things such as

* Defining functions for how things interact such as buttons, etc...
* also displays words for buttons or actions 

This is a chunk of Javascript

```Javascript
function appendData(data) {
  var cardContainer = document.getElementById("cardContainer");
  cardContainer.innerHTML = "";

  for (var i = 0; i < data.length; i++) {
    var card = document.createElement("div");
    card.className = "card";
    cardContainer.appendChild(card);

    var img = document.createElement("img");
    img.src = data[i].src;
    card.appendChild(img);

    var tagContainer = document.createElement("div");
    tagContainer.className = "tagContainer";
    card.appendChild(tagContainer);

    const tagButtons = data[i].tags.map((tag) => {
      const tagButton = document.createElement("button");
      tagButton.onclick = () => {
        const filteredCards = cards.filter((card) => {
          return (
             card.tags.find((tag) => {
               return tag.includes(tagButton.innerHTML);
             }) !== undefined
          );
        });
        appendData(filteredCards);
      };
      tagButton.innerHTML = tag;
      return tagButton;
    });
    for (const tagButton of tagButtons) {
      tagButton.className = "tagButton";
      tagContainer.appendChild(tagButton);
    }
  }
}
```

## conclusion

Front-end development is great, I have learned a lot but still need to learn more. I do not fully yet understand 

* Javascript
* some HTML

As far as I know I understand css but I still dont think I could wright it from scratch.

I will be learning these things as I progress through the year.
