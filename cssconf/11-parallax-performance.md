# Parallax Performance
by [Paul Irish](https://twitter.com/paul_irish)

"scrolling is a continuation; clicking is a decision." (quote from some other person), so long pages provide better user engagment that sites that are broken up into multiple pages.

Terminology:
* paralax: moving elemnets in the different z layers along the natural scorll pagce
* peeler: pealing of "layers" to reveal more content
* scroll jacks: taking over the natural scrolling behavriour.

When there is jank during scrolling... it means there is a "paint storm" going on (more paints than needed on the page).
Paints are the thing that drop frame rate and make mobile devices feel laggy.  

Things the browser can change super fast (using the ```transform``` CSS property):
* size
* position
* rotation
* opacity

How do we know if the user has scrolled? There are some events:
* touchstart --> delays everything
* mousewheel --> delays everything
* scroll --> adds some delay

Web Latency Benchmark: [http://google.github.io/latency-benchmark/](http://google.github.io/latency-benchmark/)  

Miniziing latency:
* bind callbacks on these events low in the DOM - avoid delegating to document because browsers always execute the handler
* bind late - don't bind stuff to non-visible elements
* unbind ASAP - if the element is gone, kill the handler
* avoid JS handlers, if you can't then debouce and bind/unbind is your friend! keep things trim.

Parallax with no JS? how is that posible? http://codepen.io/scottkellum/details/bHEcA/  <-- no paint storm!  
The Kellum/Keith technique:
* each element is palced into their own layer (z-index)

sample sites: Tomato Can BLues (from the New York Times)  
--> cool, but has some jank. why? they are modifying the ```top``` property as well as the ```transform```. elimiante the top modification... and it would work better. 

Carousel from DropBox  
--> things are smooth, but the frame rate is still really high and the experience would suck on lower powered devices (looking at the inspector panel). so they ARE only modifying the transform...if we throw in a translateZ() in there... it moves these transforatmion to their own layer and the frame rate is a lot better.  

```translateZ()``` is on its way out as a hack, there is a new property called ```will-change``` which tells the browser what property you expect to change.

paralax stuff (not good for mobile, but performant on desktop):
* skorller
* stellar.js

for mobile only... either don't do it or use the Kellum/Keith technique
