# Session 3: Frontend

## JavaScript and the DOM

## Introduction

This session we'll be making a super cool web page that shows a clock that
changes color based on the current time. But first we need to understand exactly
what this "DOM" thing is.

## The DOM

So, "DOM" stands for "Document Object Model" and this is basically a **concept**
(read: not anything concrete, not a specific file, not a certain browser, not
anything like that) that thinks about HTML documents and web pages as a
hierarchy of parent components and child components. Generally, the most
parent-level "component" would be the `<html>` tag, containing two children: a
`<head>` and a `<body>`. Also generally, the `body` component will contain many,
many children.

Something that tripped me up wrapping my head around the DOM was: _"Ok, well_
_what's the alternative then? How is the "DOM" different from the actual HTML_
_page? They look absolutely identical."_

Well, in most cases, they will! But let's take an example (absolutely beautiful)
web page:

![dog.png](https://lh6.googleusercontent.com/9cfjehIDb6_rYkUgq8bf_-skpsxf8WexJ0E0fwfsL7jyjYExLX6-2CYtx-cEyfJpUCLPx0u3LPLBOf1bmpnbFlgOVG6o3mjIDNlS3A7Uow_5JwqBnhLvjYdm0PCB2l8aCcUea79Y)

This is what the browser returns to us, as the user. It parses a certain HTML
file and generates this output. This is **not** the DOM! This is the web page!

Ok, so then let's take a look at that HTML file!

![html.png]()

As you can see, we have a `head` and a `body` and within that body we have a
heading `h1`, an image `img`, and a paragraph `p`. This is a pretty simple web page and the structure of the HTML file is not at all complicated. But this is still **not** the DOM! What's the difference?

Well, let's say that I made a mistake in my HTML file. Whoops! I accidentally
forgot to close my `<p>` tag, oh no! Now my HTML file isn't valid anymore!
But... when I go into Google Chrome, everything's fine! What gives?

This is where the differences between the HTML (the "source code" if you will)
and the DOM start to become apparent. The DOM is the representation the browser,
and ultimately, the user, have of a certain web page. And so, if the browser is
smart and/or kind enough, it will say "Oh, hey, you left out the closing p tag
here, but when I'm making the DOM, I'm pretty sure I knew what you meant so my
DOM is still just gonna have a regular paragraph, cool? 👌" And we say "Yes,
very cool thanks!!" (Don't do this in public, for some reason people are
uncomfortable if you talk to your computer 🤷‍)

The difference in the HTML file and the DOM become absolutely **huge** when you
start getting into JavaScript that renders HTML for you like React or Vue (this
is for another workshop though, one thing at a time!). The HTML file is often
incredibly simple, containing only a single `<div>` named "app" and some meta
information in the `<head>` whereas the DOM will be a fully-functional web app
with headers and sidebars and images of dogs everywhere!

That brings us to \*drum roll\* **the DOM!!!**, at last the elusive creature.

![dom.png]()

## Step 1: Creating the Folder

## Step 2: HTML

Let's start off creating an HTML file named `index.html` in our `hexclock`
directory. If you have Sublime open, just press the command `Command+N` or go to
`File` in the toolbar and click `New File`.

Make sure to give the proper extension (`.html`) so that both Sublime and the
browser know that this is an HTML file!

### General Structure

Even though the final product is gonna be super snazzy, we don't a super complex
HTML file for this one. It mostly just consists of a big clock time, a paragraph
to show the current color, and a button to change it all. This is going to all
be in the `body` of the page and the `head` will be even more simple, just
containing a title and linking to the CSS file.

Without further adieu, add this to your `index.html` file:

```html
<html>
  <head>
    <title>Hex Clock</title>
  </head>
  <body>

  </body>
</html>
```

Notice that the body is empty right now! Let's fix that.

### Body Content

We want a button so our user can change the "color modes" of our clock, some big
text showing the current time, and then some smaller text somewhere on the
bottom probably showing the current color of the clock.

Sounds pretty straightforward to me! Add this to your `body`:

```html
<button id="changeColorMode">Change color mode!</button>
<h1 id="clock">00:00:00</h1>
<p id="hex"></p>
```

If you need a refresher from our first workshop, the `id` attributes are how you
target a specific element. Before, we used this for CSS styling, but this time
around, it's even more important! This time, we'll be using the `id` attributes
to manipulate the DOM! We need a unique `id` for each of our elements for easier
manipulation and since this is a smaller web page, it's no problem at all to
make these IDs. 💪

Believe it or not, our HTML file is (almost mostly) done! Let's move on to
styling.

## Step 3: Styles

Create a new file called `style.css` in the same `hexclock` directory we made.
You want this to be in the same folder as the `index.html` at any rate.

### Fonts

We here at ACM are big on branding! And like any good developers we love our
fonts. ✏️ We're gonna be importing our main font "Poppins" from Google Fonts.

Add this line to the beginning of your `style.css` file:

```css
@import url("https://fonts.googleapis.com/css?family=Poppins:700");
```

This basically loads in the Poppins font (at a weight of 700 in case you
wondering about the number) so that we can use it in our styles super simply.

### Body Styles

I'm a big fan of having no margin, no padding `body`s. To use our lovely font
Poppins imported above, we're just gonna treat it like any other font, with the
exception that you have to put quotes around its name when referencing it.

Copy and paste this CSS rule into your file:

```css
body {
  margin: 0;
  padding: 0;
  font-family: "Poppins", sans-serif;
  font-size: 64px;
  color: white;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
}
```

If you're not familiar with flex boxes, well get ready because next week we're
gonna have a whole workshop on the magic and the madness of CSS centering. For
now, just know that the body is going to align everything nice and pretty for
us. ✨✨✨

### Paragraph and Button

These styles are pretty simple. Just add the following:

```css
p {
  font-size: 24px;
}
button {
  padding: 1em 2em;
  font-size: 18px;
  font-family: "Poppins", sans-serif;
  border-radius: 10px;
}
```

The button styles are just to give it some nice padding so it looks big and
clickable.

## Step 4: Scripting

## Step 5: oooh pretty clock!
