#The Chroma Zone: Engineering Colors on the Web
by [Lea Verou](http://twitter.com/leaverou)

RGB is a color system that is much closer to "the machine" and is not really intended to be human readable.  
Hex colos are not much better... stil not intutive.  
HSL (hue, saturation, lightness) was better. It's a bit more intutive and better than the others, but still not great yet. And HSL gives you the ability to apply SVG filters (with a decent notation) and they are combinable, so you can colorize images. (not supported in all browsers as yet, but the spec is there)  

CSS blend modes = ability to use all the Photoshop blending mods in the browser. The spec is out there, but not ready for production as yet.  

luminence !== lightness  

spec is also working on a new keyword (or variale) named ```currentColor``` and is supported in native CSS (back to IE9) - [http://css-tricks.com/currentcolor/](http://css-tricks.com/currentcolor/)  

CSS varibles are coming  

disclaimer: CSS Color Level 4 is still an initial draft (from all notes below this comment)  

* some clors will become functions- like gray (gray(50%)) to changes the level of gray.  
* maybe the ability to have semi-transparent hex values (add a sigle chracter value at the end)
* new color format HWB (hue, whiteness, blackness) - HWB !== HSB
* new ```color()``` function which has a few "adjusters" (like "tint", "shade", "blend", and many more) 
* reg() and hsl() will accept alpha values


All slides are here: [https://github.com/LeaVerou/css-colors](https://github.com/LeaVerou/css-colors)
