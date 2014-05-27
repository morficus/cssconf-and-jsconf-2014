# What is Perspective
by [Evangelina Ferreira](http://www.evaferreira.com.ar/)

slides: [http://www.evaferreira.com.ar/perspective/](http://www.evaferreira.com.ar/perspective/)

Perspective has 3 elements:
* point of sight
* horzontal line (or horizon)
* vanishing point

So how does this apply to CSS and web design?  

Using the ```transform``` property, we can change an elements perspective.  (the origin is the center by default)
we can also use ```transform-origin```, to make that not the center. (basically move it anywhere around the element) --> but we can set the origin...outside of the element (aka: a 200px element, with a 400px 0 origin point). This causes problems.  
We can solve these problems by adding a "father" (or parent) element.  

```css
.father {
  transform: perspective(200px);
  }

.child {
  transform: rotateX(90deg);
}
```

```backface-visibility``` property indicates if a "back side" of an element should be visible or not (visible my default). This matters when rotating elements on a 3D plane.  

Transforms can be mixed together (either rotations or translations, on the 2d or 3d plane).  
ie: 
```css
.father {
  transform: translateX(45px) translateY(45px) translatee(45px)
}
```
Is the same as...
```css
transform: translate3d(45px, 45px, 45px)
```

Webkit we needs prefixes (for now), Firefox does not, and IE dos not have 3d
