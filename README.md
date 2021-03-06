# Intro to HTML and CSS


## Requirements

We'll need two things for this lesson. A good text editor and Google Chrome. We're going to standardize the use of Google Chrome for this particular lesson thanks to something called [vendor prefixes](http://css-tricks.com/how-to-deal-with-vendor-prefixes/). However, if Google Chrome isn't your favorite browser, feel free to ask a mentor how you can make your project run in Firefox or other modern browsers.

### Windows

Download and install **Notepad++**

* [http://download.tuxfamily.org/notepadplus/6.1.3/npp.6.1.3.Installer.exe](http://download.tuxfamily.org/notepadplus/6.1.3/npp.6.1.3.Installer.exe)

Download and install **Google Chrome**
* [http://google.com/chrome](http://google.com/chrome)

### Mac OSX

Download and open **Text Wrangler**

* [http://ash.barebones.com/TextWrangler_4.0.1.dmg](http://ash.barebones.com/TextWrangler_4.0.1.dmg)

Download and open **Google Chrome**

* [http://google.com/chrome](http://google.com/chrome)


## What is HTML and CSS?

HTML (Hyper Text Markup Language) and CSS (Cascading Style Sheets) work together to create every webpage you see on the Internet. 

That may sound intimidating at first so let's start out with a real life example. We're going to pretend that I, *a human being*, am a website.

A website is made up of many things. There are tables, forms, navigation bars, paragraphs, headings, and more. 

I'm also made up of many things. I'm wearing a shirt, a pair of shoes, a belt, a pair of pants, maybe even a shirt on top of my shirt. If I were an HTML document, these would be all of my "elements". However, you may notice that my clothes look very different than your own. I probably wear a different size, different colors, different shapes, and maybe they even have different features.  With CSS, we can describe how all of the elements on my "page" should look.

```html
<div class="shirt"> 
John's Shirt
</div>
```

```css
.shirt {
	color: #000000;
	collar-type: button-down;
	pattern: solid;
	size: small;
	button-spacing: 3in;
}
```

The CSS describes all of the things that makes my shirt unique. Just as my shirt probably doesn't look like the one that you are wearing, my website probably doesn't look like your website. 

We all know that you can't code a T-Shirt so let's take a look at what a real website looks like. 


## Using Chrome Developer Tools

Chrome has done us the favor of including some wonderful development tools into the web browser that you're already using. They're not only a great way to see how someone else made that really cool hover effect, but also a great way to experiment in real time without having to constantly refresh the page you are working on.

To start, load up your favorite website. Mine is http://diy.org

### Inspect an Element

The inspect tool is one of the tools we will be playing with today. The inspect tool can tell you everything there is to know about an element on the page. To inspect something, just right click on it and select "inspect element"

If you already have your developer tools open, you can click the magnifying glass in the bottom-left corner of the screen and then simply click on the element that you want to inspect.

Now that you've selected an element, take a look at the right hand side of the screen. This is where you'll see the CSS code that is describing the selected element. 

```css				
pre {
	background-color: #f8f8f8;
	border: 1px solid #ccc;
	font-size: 13px;
	line-height: 19px;
	overflow: auto;
	padding: 6px 10px;
	border-radius: 3px;
}
```

A great thing about this tool is how you can make edits to these   properties and see your changes in real time. Try clicking once on a number (like 13px in **font-size: 13px**) and use the up and down arrow keys on your keyboard to watch it change.

### Edit HTML

You may also want to edit your HTML in real time. Chrome makes this easy. Simply right the text that goes with the element you are inspecting and click "Edit as HTML"

To "save" your changes simply click outside of the edit window.

**Warning: If you refresh your web page, any modifications that you made to the page within Chrome Developer Tools will not be saved**


## Creating Your Website

Open up your preferred text editor and we're going to create two files. 

	index.html
 	styles.css

For simplicity's sake, be sure to save them in the same folder.

Let's work with the HTML file first. We're going to set up the basic framework for a webpage.

### Building your Index.html file

Our HTML file is going to be pretty basic at first. 

```html
<html> 
	<head>
		<title> John's Cool Website </title>
	</head>
	<body>
		<h1> Hello! </h1>
	</body>
</html>
```

One more thing! We didn't create that CSS file for nothing so let's make sure that the HTML file knows that it exists. Add the following line to your `<head>`

	<link rel="stylesheet" href="styles.css">

### Building your styles.css file

So far, we don't have a whole lot of elements on our page that we can modify. There is a header and a body. But we'll work with that just to make sure that our stylesheet is being referenced properly.

Let's change the background color to blue.

```css
.body {
	background-color: blue;
}
```

Save your changes and refresh your page, the background should now be blue!

### What's next?

So far, all of this is pretty plain but CSS can actually do some pretty neat stuff. Take a look at https://github.com/404 for a taste of the kind of thing we'll be making.

## Creating our animated object

What is an animation in CSS? Essentially, an animation is just a gradual change of the css properties that define an element. You determine how many "steps" there are to the animation, how long it lasts, when it starts, and a [bunch of other stuff](http://www.w3schools.com/css3/css3_animations.asp)

With that said, we are going to create a heart and use some CSS animations to make it beat.

### Start the heart

All good hearts start out as a square. A great philosopher once said that, I think. To keep things simple let's draw a simple square on our page.

The first thing we're going to do is create a "container" for the heart. We'll give it an id of "chest" because... that's where hearts go.

In your index.html file.
```html
  <body>
    <div id="chest">
    </div>  
  </body>
```

and define some properties for this chest in styles.css

```css 
#chest {
  position:relative;
  width:500px;
  height:450px;
  margin:0 auto;
}
```

Now, let's put a "box" inside that chest.

In your index.html
```html
<div id="chest">
	<div class="heart"></div>
</div>
```

In your styles.css
```css
.heart {
  position:absolute;
  z-index:2;
  background: #B80734;
}
```

Well, that didn't do anything exciting. That's because we described very little about the heart. In CSS, it is common that you will often describe a div with multiple classes. Right now, the only thing we are describing is that inside the "chest" there is a "heart" and you may notice that we haven't said how big the heart is or where it is located. 

Let's add another class called "center" that will describe what the first piece of the heart will look like.

In your styles.css
```css
.center {
  width:210px;
  height:210px;
  bottom:100px;
  left:145px;
}
```

and don't forget to apply that class to your div, in addition to the "heart" class.

```html
<div class="heart center"></div>
```

Now you should see something!

There are a few different ways to build a heart. We're going to be doing it by drawing two circles and using one square. However, don't be afraid to try your own way!

The next step is going to be to add the two side circles that will make up the top part of the heart. To do that, we'll create another CSS class called "side"

```css
.side {
  top:50px;
  width:220px;
  height:220px;
}
```

and let's add some more squares to our HTML and apply the side class.

```html
  <body>
    <div id="chest">
      <div class="heart side "></div>
      <div class="heart center"></div>
      <div class="heart side"></div>
    </div>  
  </body>
```

Now... let's turn those side squares into circles. Edit your "side" class to add a border radius.

```css
.side {
  top:50px;
  width:220px;
  height:220px;
  -webkit-border-radius: 110px;
}
```

Awesome! When using the border radius to create a circle, be sure to make your border radius at least half as many pixels as the width and height. If you just want rounded corners, you can use less. 

Alright, so our circles are stacked on top of eachother and that's no good. Let's define a left side and a right side class. 

In your styles.css
```css
.left {
  left:62px;
}

.right {
  right:62px;
}
```

and in your index.html we'll apply them.

```html
  <body>
    <div id="chest">
      <div class="heart side left"></div>
      <div class="heart center"></div>
      <div class="heart side right"></div>
    </div>  
  </body>
```

### It lives!

Now, let's animate.

We're going to describe some keyframes at the top of the CSS file. This will tell our elements what to do during the animation.

```css
@-webkit-keyframes beat {
  0% {-webkit-transform: scale(1.2) rotate(225deg); -webkit-box-shadow:10px 5px 10px rgba(213,9,60,0.9);}
  50% {-webkit-transform: scale(1) rotate(225deg); -webkit-box-shadow:10px 0 10px rgba(213,9,60,0.4);}
  100% {-webkit-transform: scale(1.2) rotate(225deg); -webkit-box-shadow:10px 0 10px rgba(213,9,60,0.9);}
}
```

but hold on one second. We need to apply this animation that we called "beat" to a class. Let's apply it to the heart class so the "heart" will beat.

```css
.heart {
  position:absolute;
  z-index:2;
  background: #B80734;
  -webkit-animation: beat .7s ease 0s infinite normal;
}
```
Magic!

One more thing... That might look a little ugly so remember that z-index we used? That tells the HTML how things should stack on top of each other. Let's make sure the left side is the highest in the stack.

```css
.left {
  left:62px;
  z-index: 3;
}
```


## Extra Credit

- Make the heart move around on the screen while it is beating.
- Make it rotate!

		
