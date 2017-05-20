# MG Neat

One day, I read this article about a different way of thinking about browser breakpoints than I was used to:

[The 100% correct way to do CSS breakpoints](https://medium.freecodecamp.com/the-100-correct-way-to-do-css-breakpoints-88d6a5ba1862)

Then, another day, I thought, "I wish there was a grid framework that used these breakpoints".

## Introducing MG Neat

MG Neat is a small grid (only) framework that provides classes you can use to make a responsive 12-column grid based on these breakpoints:

```
@mixin for-phone-only {
	@media (max-width: 599px) { @content; }
}

@mixin for-tablet-portrait-up {
	@media (min-width: 600px) { @content; }
}

@mixin for-tablet-landscape-up {
	@media (min-width: 900px) { @content; }
}

@mixin for-desktop-up {
	@media (min-width: 1200px) { @content; }
}

@mixin for-big-desktop-up {
	@media (min-width: 1800px) { @content; }
}
```

That's right! It even comes with handy mixins.

## Installation

To get started, you can just import the CSS file:

```
<link rel="stylesheet" href="grid.css">
```

MG Neat is built with Bourbon Neat. You can use the SCSS files to build it yourself (and change it!). You will need to run `npm install` in the MG Neat directory. This will install Bourbon Neat into your project.

## Usage

Grid markup looks like this:

```
<div class="container">
	<div class="row">
		<div class="col-6"></div>
		<div class="col-6"></div>
	</div>
</div>
```

### Static grid elements

Grid columns using the `.col-#` classes remain constant, proportionally, regardless of the viewport width. 

### Responsive grid elements

Grid columns using the responsive grid classes adapt based on the viewport width.

- `.phone-#` (phone only)
- `.tablet-port-#` (tablet portrait and up)
- `.tablet-land-#` (tablet landscape and up)
- `.desktop-#` (desktop and up)
- `.big-#` (big desktop and up)

```
<div class="container">
	<div class="row">
		<div class="phone-12 tablet-port-6 desktop-4"></div>
		<div class="phone-12 tablet-port-6 desktop-8"></div>
	</div>
</div>
```

### Push and shift

Use `.push-#` and its responsive equivalents (e.g., `.phone-push-#`) to move a grid element over using its left margin.

Use `.shift-right-#`/`.shift-left-#` and its responsive equivalents (e.g., `.phone-shift-right-#`) to reorder grid elements within their container using relative positioning.

## Demo

For a better look, load up the demo file in your browser.