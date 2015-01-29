# inline
css grid component that doesn't use floats. Supports all browsers if taking a [Progressive Enahancement](http://alistapart.com/article/understandingprogressiveenhancement) approach (e.g. this code should not trigger nor break in those browsers; see [#3](https://github.com/kevinpeno/inline/issues/3))

Why? Because floats need to die in a fire! http://jsfiddle.net/4s7R6/29/

Example usage:
```less
.test {
	.inline-grid(1em);

	> * {
		.inline-column(1/12);
	}
}
```

Will output:
```css
.test {
  font-family: monospace, monospace;
  letter-spacing: -0.6em;
  letter-spacing: -1ch;
  box-sizing: border-box;
  padding-left: 0.5em;
  padding-right: 0.5em;
}
.test > * {
  font-family: sans-serif;
  letter-spacing: normal;
  box-sizing: border-box;
  padding-left: 0.5em;
  padding-right: 0.5em;
}
.test > * {
  width: 8.33333333%;
  display: inline-block;
}
```