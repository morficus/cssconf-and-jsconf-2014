# CSS In Your Pocket (mobile CSS tips from the trenches)
by [Angelina Fabbro](http://twitter.com/angelinamagnum)

Mobile is "a thing" now, and we can't denny it. There are many good tools out there to help with CSS debugging, but no one tool solves all my problems.  

There are 2 type of CSS debugging on mobile:
* layout
* performance  

Cross-browser/cross-device isses - these are all layout issues:    

Android 2.3 is "the new" IE6 - here are some common pitfalls:
* ```position: fixed``` does not work very well on mobile (even versions of iOS). There are some hacks... but some of them cause perfoamnce issues.
* min-height, -width, max-height, -iwdht behave inconsistently
* ```overflow: auto``` is also inconistent...
* z-index does not apply to absolutley positioned elements. fix? add a ```z-index: 0``` on the body.
* ems are poorly supported, rems are not supported at all.
* no gradients
* media queries give @portrait dimentions, even after rotating the device...


More resourece:
* [http://www.quirksmode.org/](http://www.quirksmode.org/)
* [http://www.charlesproxy.com/](http://www.charlesproxy.com/)

These are typically known to cause perfoamnce issues on mobile:
* "*" selector
* really long classnames
* broder-radius
* box-shadow
* transforms

