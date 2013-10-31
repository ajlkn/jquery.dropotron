# jquery.dropotron: Multilevel dropdown menus for jQuery

Adds multilevel dropdown menus to jQuery. Way customizable and stuff.

## Usage

Load it after jQuery:

```html
<script src="http://code.jquery.com/jquery-x.x.x.min.js"></script>
<script src="jquery.dropotron.min.js"></script>
```

Set up your menu:

```html
<nav id="main-nav">
  <ul>
    <li><a href="/">Home</a></li>
    <li>
      <a href="/skills">Skills</a>
      <ul>
        <li><a href="/skills/nunchuks">Nunchuks</a></li>
        <li><a href="/skills/bow-hunting">Bow Hunting</a></li>
        <li><a href="/skills/computer-hacking">Computer Hacking</a></li>
        <li><a href="/skills/disco">Disco</a></li>
      </ul>
    </li>
    <li>
      <a href="/enemies">Enemies</a>
      <ul>
        <li><a href="/enemies/don">Don</a></li>
        <li><a href="/enemies/uncle-rico">Uncle Rico</a></li>
        <li>
          <a href="/enemies/rogue-ais">Rogue AIs ...</a>
          <ul>
            <li><a href="/enemies/rogue-ais/shodan">SHODAN</a></li>
            <li><a href="/enemies/rogue-ais/wintermute">Wintermute</a></li>
            <li><a href="/enemies/rogue-ais/neuromancer">Neuromancer</a></li>
            <li><a href="/enemies/rogue-ais/deus">Deus</a></li>
            <li><a href="/enemies/rogue-ais/megaera">Megaera</a></li>
          </ul>
        </li>
        <li><a href="/enemies/chickens">Chickens</a></li>
      </ul>
    </li>
    <li><a href="/art">Art</a></li>
    <li><a href="/contact">Contact</a></li>
  </ul>
</nav>
```

Throw in a bit of styling:

```css
#main-nav ul { list-style: none; margin: 0; padding: 0; }
#main-nav ul li { display: inline-block; margin: 0 1em 0 1em; padding: 0.35em 0.75em 0.35em 0.75em; border-radius: 0.5em; }
#main-nav ul li.active { background: #999; }
#main-nav ul li.active a { color: #fff; text-decoration: none; }
.dropotron { background: #444; border-radius: 0.5em; list-style: none; margin: 0; min-width: 10em; padding: 0.75em 1em 0.75em 1em; }
.dropotron > li { border-top: solid 1px #555; margin: 0; padding: 0; }
.dropotron > li:first-child { border-top: 0; }
.dropotron > li > a { color: #ccc; display: block; padding: 0.5em 0 0.5em 0; text-decoration: none; }
.dropotron > li.active > a, .dropotron > li:hover > a { color: #fff; }
.dropotron.level-0 { margin-top: 1.25em; }
.dropotron.level-0:before { content: ''; position: absolute; border-bottom: solid 0.5em #444; border-left: solid 0.5em transparent; border-right: solid 0.5em transparent; top: -0.5em; }
```

And finally, call dropotron() on the menu's top level <ul>:

```js
var foo = $('#main-nav > ul');
foo.dropotron();
```

That's about it.

## Config

dropotron() can optionally override some or all of the following defaults:

```js
foo.dropotron({
	selectorParent:		null,		// Parent jQuery object
	baseZIndex:			1000,		// Base Z-Index
	menuClass:			'dropotron',// Menu class (assigned to every <ul>)
	expandMode:			'hover',	// Expansion mode ("hover" or "click")
	hoverDelay:			150,		// Hover delay (in ms)
	hideDelay:			250,		// Hide delay (in ms; 0 disables)
	openerClass:		'opener',	// Opener class
	openerActiveClass:	'active',	// Active opener class
	submenuClassPrefix:	'level-',	// Submenu class prefix
	mode:				'fade',		// Menu mode ("instant", "fade", "slide", "zoom")
	speed:				'fast',		// Menu speed ("fast", "slow", or ms)
	easing:				'swing',	// Easing mode ("swing", "linear")
	alignment:			'left',		// Alignment ("left", "center", "right")
	offsetX:			0,			// Submenu offset X
	offsetY:			0,			// Submenu offset Y
	globalOffsetY:		0,			// Global offset Y
	IEOffsetX:			0,			// IE Offset X
	IEOffsetY:			0,			// IE Offset Y
	noOpenerFade:		true,		// If true and mode = "fade", prevents top-level opener fade effect.
	detach:				true,		// Detach second level menus (to prevent parent styling from bleeding through).
	cloneOnDetach:		true		// If true and detach = true, leave original menu structure intact.
});
```

## License

jquery.dropotron.js is released under the MIT license.

Copyright © 2013 n33

Permission is hereby granted, free of charge, to any person obtaining a
copy of this software and associated documentation files (the
"Software"), to deal in the Software without restriction, including
without limitation the rights to use, copy, modify, merge, publish,
distribute, sublicense, and/or sell copies of the Software, and to
permit persons to whom the Software is furnished to do so, subject to
the following conditions:

The above copyright notice and this permission notice shall be included
in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS
OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF
MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT.
IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY
CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT,
TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE
SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
