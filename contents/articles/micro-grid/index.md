title: Micro Grid
author: Juan Olvera
date: 2013-04-20 12:00
template: article.jade

*A Tiny 12 column fluid grid generator. [Source-code](http://github.com/thinkxl/micro-grid) and [live demo](http://thinkxl.github.io/micro-grid/)*

Recently, one of my favorite tools [cssgrid](http://andytaylor.me/2013/04/09/1140px-css-grid-retired/) was deprecated, an excellent fluid grid, so I decided to make my own... with [less](http://lesscss.org) btw.

But first I wanted to solve some problems or things I dislike from grids.

- Fixed size of gutter.
- I don't use all the columns on every project, and delete code for each one is not an option.
- A lot of code for a simple need, (cssgrid solved this very well).

The result project is [micro-grid.less](http://github.com/thinkxl/micro-grid), that is not a grid itself, is a function that can generate a customized one automatically, just entering the number of columns I need, for example:

```css
@import 'micro-grid';
@gutter: 2%; /* set our gutter size, 1% by default */

.cols(1); /* equal to a 100% width */
.cols(2); /* this one 50% and so on... */
```

Now I'm able to build a grid with only the columns I need on a certain project.

For example if I need to make a layout with 3 columns:

**less**
```css
@import 'micro-grid';

/* container */
.main {
	max-width: 60em;
	margin: 0 auto;
	padding: 1em;
}

/* one of three columns, 12/3 = 4 */
.col-1-3 { .grids(4); }
```

**markup**
```xml
<div class="main">
	<div class="grid">
		<div class="col-1-3">
			<p> lorem ipsum </p>
		</div>

		<div class="col-1-3">
			<p> lorem ipsum </p>
		</div>

		<div class="col-1-3 last">
			<p> lorem ipsum </p>
		</div> <!-- note that we add last to our last div -->
	</div> <!-- end of grid -->
</div> <!-- end of main -->
```

And that's all!, I don't have to worry about ugly % calculations anymore, just trust my less function.

I just compile the columns that I need, the *micro-grid.less* file is *0.334 kb uncompressed* so is a powerful tool on a very good size.

You can download the source-code and view full documentation on [GitHub](https://github.com/thinkxl/micro-grid) and check the live [demo](http://thinkxl.github.io/micro-grid/).

Happy coding!
