# Bulletproof Font Icons
by [Zach Leatherman](http://twitter.com/zachleat)

There are many font formats, you only need to care about 4:
* WOFF: supported by most modern browsers
* TFF: for Android support
* EOT: for IE8 support
* SVG: for Chrome only on Windows XP (Chrome on XP supports WOFF, but some fonts look janky because of the rending engine. This will be fixed in a future stabe release of Chrome)


But with using SVG... you need to be careful. Chrome for windows supposets TFF, and it will try to apply the first one that it finds.

By including the @font-family rule w/o using it, it won't get downloaded (expect in IE8). Only when you apply it in a class... then it will get downlaoded by the browser.  

Unicode!  
Every unicode "code" has a specific meaning. This is how you can use the same unicode across devices and fonts but still end up with the same symbol.  
There are higher-number unicode characters, which are used for stuff like emjojis.
There is also a private user area (PAU) which is a REALLY high unicode number, which is resserved for custom characters. This is what custom font-icon develoeprs use to avoide collisions with standard characters.    

Because of this PUA, since there is no "fallback" chracter, the browser shows blank text (knows as flash of invisible text [FOIT]) or an unidentfiable chracter ( known as flash of unstyled text [FAUT]) until it the font downloads. This is particualrly troublesum for content fonts.  

There is a full write up along with techniques to (try) and solve this problem here: [http://filamentgroup.com/lab/bulletproof_icon_fonts.html](http://filamentgroup.com/lab/bulletproof_icon_fonts.html)
