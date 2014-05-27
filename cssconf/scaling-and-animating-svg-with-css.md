# Styling & Animating SVG's with CSS
by [Sara Soueidan](http://twitter.com/SaraSoueidan)

Most SVG-genrating tools out there (Ilustrator, etc) export "dirty" code with lots of meta-data that is unecesary.  
Recomend using something like "SVG Editor" [http://petercollingridge.appspot.com/svg-editor?_sm_au_=iVVsLNMMV4NL7Qkr](http://petercollingridge.appspot.com/svg-editor?_sm_au_=iVVsLNMMV4NL7Qkr) to clean this up before styling and animating, or this: https://github.com/svg/svgo  

You will also want to change the genric generated names to something more semantic that makes sense to you or your project.  

A sub-set of the SVG properties are shard wit the CSS, not everything can be done in CSS since some are SVG only.  

The styles can either be embded in the SVG file or externally.  

SVG styles are stil subject to the cascade.  

The recomended method of adding SVG's to the page is via the ```svg``` tag or the ```object``` tag if you want a fallback.  
Animations are not preseved if you embed using an ```img``` tag, unless you're using an svg animation.  

```transform-origin``` for SVG elements are taken from position 0 0 (top left corner for the canvas), while with HTML elements it's taken at 50% 50% (center of the element).  This mean we need to change the transform-origin when dealing with rotations on SVG elements.  

To animate and draw an SVG path, you will need to know its final length. This is the trick to makeing it simple.  
If you don't know it ahead of time, you can get it with JS (path.getTotalLength()).  
Cool demo: http://blog.studio.gd/blog/id/6/how_to_use_svg_in_your_html_-_part_1-3  

For mophing SVG paths, there is currenlty no way to do so with CSS. Recomendation is to use snap.svg (http://snapsvg.io/)  

Some recomended reading:  
* [http://oak.is/thinking/animated-svgs/](http://oak.is/thinking/animated-svgs/)
* [http://filamentgroup.com/lab/artifact-austin-svg-workflow.html](http://filamentgroup.com/lab/artifact-austin-svg-workflow.html)
