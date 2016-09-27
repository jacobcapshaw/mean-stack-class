#MEAN Session One

Read of the day: [Why Learning Angular Two was Excrutiating](https://hackernoon.com/why-learning-angular-2-was-excruciating-d50dc28acc8a#.9px57nno9)

Python Simple Server `python -m SimpleHTTPServer <port>`

##Base CSS

box model - `box-sizing: border-box;`

```
<link rel="stylesheet" type="text/css" href="css/styles.css">

* {
	margin:0;
	padding: 0;
	box-sizing: border-box;
}

ul {
	list-style: none;
}

html, body {
	margin: 0; 
	color: #333; 
	font-size: 100%; 
	font-family: Helvetica, Arial, sans-serif; 
}

.wrapper {
  max-width: 67em;
  margin: 0 auto;
  position: relative;
}

nav {
	margin-bottom: 1em;
}

nav ul { 
	list-style: none; 
}

nav li {
	display: inline-block;
	margin-right: 1em;
}

nav a {
	color: #333;
	text-decoration: none;
	padding: .5em;
	display: block;
	background-color: #f0dfb4
}

nav a:hover {
	color: #fff;
	background-color: #600;
}

.info {
	position: absolute;
	top: 10em;
	left: 0;
	width: 10em;
	background-color: #F0DFB4;
	padding: .5em;
	border: 1px solid #600;
}

article {
	margin: 2em 0 0 12em;
}

blockquote  {
	float: right;
	width: 40%;
	padding: 1em;
	font-size: 1.5em;
}
article img {
	float:  right;
}

p {
	margin: 1em 0;
}
```

##Responsive

* Mobile first design. 

Try: 740px

* 81.25em = 1300px
* 71.25em = 1140px
* 61.25em = 980px
* 46.25em = 740px
* 22.5em = 360px

```
@media (max-width: 46.25em) {
    blockquote {
        width: 100%;
    }
}

@media (max-width: 46.25em) {
    .info {
        position: static;
        width: 100%;
    }
}

@media (max-width: 46.25em) {
    article {
        margin-left: 1em;
    }
}

```

Then try implementing mobile first in CSS by making the default CSS work for small screens and the media queries work for large screen.

[Stack Overflow](http://stackoverflow.com/questions/19472199/why-does-mobile-first-responsive-design-tend-to-not-use-max-width-queries-alongs#19515469)

[CSS Tricks](https://css-tricks.com/logic-in-media-queries/)

```
.info {
	position: static;
	width: 100%;
	background-color: #F0DFB4;
	padding: .5em;
	border: 1px solid #600;
}

@media (min-width: 46.25em) {
	.info {
		position: absolute;
		top: 10em;
		left: 0;
		width: 10em;
		
	}
}

article {
	margin-left: 1em;
}

@media (min-width: 46.25em) {
	article {
		margin: 2em 0 0 12em;
	}
}

blockquote  {
	width: 100%;
	padding: 1em;
	font-size: 1.5em;
}

@media (min-width: 46.25em) {
	blockquote {
		float: right;
		width: 40%;
	}
}

<meta name="viewport" content="width=device-width, initial-scale=1.0">
```

[Viewport Demo](http://daniel.deverell.com/css-files/responsive-meta-example/)

##SASS

* OSX koala
* comments
* error checking
* variables
* imports and structure

```
@import "imports/variables";
@import "imports/basics";

$tan: #f0dfb4;
$reddish: #600;
$dark-gray: #333;
$white: #fff;
```

* nesting

```
nav {
	margin-bottom: 1em;
	ul { 
		list-style: none; 
	}
	li {
		display: inline-block;
		margin-right: 1em;
	}
	a {
		color: $dark-gray;
		text-decoration: none;
		padding: .5em;
		display: block;
		background-color: $tan;
	}
	a:hover {
		color: $white;
		background-color: $redish;
	}
}

.info {
	position: static;
	width: 100%;
	background-color: $tan;
	padding: .5em;
	border: 1px solid $reddish;

	@media (min-width: $break-one) {
		position: absolute;
		top: 10em;
		left: 0;
		width: 10em;
	}
}

article {
	margin-left: 1em;
	@media (min-width: $break-one) {
		margin: 2em 0 0 12em;
	}
}

blockquote  {
	width: 100%;
	padding: 1em;
	font-size: 1.5em;
	@media (min-width: $break-one) {
		float: right;
		width: 40%;
	}
}

padding: $padding*3 0;
```

[Bootstrap SASS](https://github.com/twbs/bootstrap-sass)

##Second Page

###Static Pages
* static app - anchor in browser > request to server > database > html > browser
* AJAX - ability to refresh data after the app is running (mapquest vs google maps)
* Progressive enhancement - a trap?
* Spaghetti Javascript - code modifies existing DOM vs code that creates the DOM
* Mobile native (receives json) vs browser native (receives html)

###Thick client
* Modern web architecture - browser requests html > page contains JS that builds the base structure > ajax loads content via json > JS modifies DOM to present content.
* Benefits - same code for mobile and web, performance leverages the client (distributed), standardization on JS, html and css, speed and increased modularity.
* Routing

```
<body class="p-cuisines">

<li><a class="t-cuisines" href="#">Cuisines</a></li> 
<li><a class="t-recipes" href="#">Recipes</a></li>

.p-cuisines .t-cuisines { 
	color: #fff; 
	background:#600; 
} 
```

##Google font

```
@import url('http://fonts.googleapis.com/css?family=Lato:300,400,700');
$font-family: 'Lato', sans-serif;
```

##Homework

1. Improve the look and feel (e.g. 'design') of the existing page for both large and small screens using SASS (use rounded corners, Google fonts, color, etc.).
1. Create a second html recipe page that you can navigate to. The nav bar should indicate which section you are in using color. 
1. Use a [schema](http://schema.org/Recipe) to mark up this data. 
1. Buy texts, open a Github account, install node on your laptop

##Reading
Ethan Marcotte - [Responsive Web Design](https://abookapart.com/products/responsive-web-design)
Dan Cederholm - [SASS for Web Designers](https://abookapart.com/products/sass-for-web-designers)

###TBD
* modernizr `http://www.colorzilla.com/gradient-editor/ `
* GIT and Github
