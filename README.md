# jQuery Easing Molecules

A rebuild of the common [jQuery Easing plugin](http://gsgd.co.uk/sandbox/jquery/easing/) using simpler code and the building block style used by MooTools and D3.

## What does it do?

Currently it provides all the usual easing types in the jQuery Easing plugin, but in a smaller, re-usable way.
Soon it will also provide a keyframe-style easing builder to create custom multi-part easing functions, but that's still in development right now.

## Background

A quick timeline of easing in jQuery:

* 2003 - [Robert Penner](http://www.robertpenner.com/easing) created the first easing functions for Flash, with parameters for Current Time, Start Value, End Value, Total Duration.
* 2007 - jQuery 1.1 released with easing support, mostly using Penner's function signature but with an additional (first) parameter for the percentage of duration.
* 2007 - [George Smith](http://gsgd.co.uk/) ported Penner's original functions to jQuery, ignoring the extra Percentage parameter. These have been copied verbatim into projects for 5 years - including jQuery UI (with only a couple of minor tweaks).

However, other JavaScript libraries like [Dojo](http://dojotoolkit.org/), [Scriptaculous](http://script.aculo.us/), [MooTools](http://mootools.net/) and  [Raphaël](http://raphaeljs.com/) realised that Penner's system could be simplified.
The percentage of time elapsed is the only thing that really matters to an easing function, and every one of Penner's equations had to calculate that percentage using 4 function parameters.
These libraries removed all function arguments except for percentage - everything else is handled within the library.

MooTools and, later, [D3](https://github.com/mbostock/d3) made even more improvements by breaking down the repetitive parts of Penner's equations into small, reusable pieces.

### What's with all the hating on Penner?

None at all! Penner's system and equations revolutionised the way people programmed animations in Flash, taking animation customisation away from a purely GUI-based system and putting it in the hands of developers.
Penner's original system was perfect for what it was required to do (in the ActionScript 1 compiler), and it's a testament to his ingenuity that the same basic equations are still being used in multiple major libraries today, across different languages.
