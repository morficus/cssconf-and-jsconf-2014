# Style Guide Driven Devleopment
by [Nicole Sullivan](http://twitter.com/stubbornella)


__Problems:__
* lots of CSS (91% unused on a standard page)
* really difcult to work with
* layout profiliferation (~7 different layouts that were not very different...)
* partials in partials.... for just the sake of having partials
* jQuery soup - custome one-off widgets everywhere

Live stylleguide: [https://console.run.pivotal.io/style_guide](https://console.run.pivotal.io/style_guide) (generated using with [http://trulia.github.io/hologram/](http://trulia.github.io/hologram/))

Initially did not try to make the "most optimal system", just a system which you can iterate over.  
The goal was to make reusable components that folks just pick up and go.  
Current issue with the styleguide is that is is getting difficult to find stuff with in the categories and such.  


__Hypothesis:__ components should be hard, pages should be easy (a page has multiple components)  

Documentation lives next to the CSS. The generator allows you to place Markdown into the coments of your CSS.  
Documentation includes sample markup to demonstrate what the HTML structure should be.  


Process issues: who defines a "component"? Designer or devleoper?  
Answer: it's everyones job. this was solved wtih close colaboration initally.  


__But what makes a "good component"?__
* should be small (correct granulairty)
* fleixbility (what do you not know? particualrly width and height)
* low specificity
* encapsulation
* some level of predictability (ie: image always on the left, regardless of size)


__Thanks that worked really well:__
* design & dev pairing: awesome for nailing down animation and transitions
* color and spacing tweaks when didn't match the mockup
* general refinements


__Results:__
* no more view-specific CSS
* much easier to manage CSS code base (higher velocity in sprints)
* scope is eaier to determien (more accurate estiamtes)
* design is consistent (in place of looking at pages, would check the style guide)


The mentality changes...  
berfore: what markup/CSS do I need to write?  
after: which compoennts is this page made of?  
