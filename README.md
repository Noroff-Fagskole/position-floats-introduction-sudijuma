<img src="./.readme/noroff-light.png" width="160" align="right">

# Positioning &amp; Floats introduction

## Demo 1: float

If you want to place an image beside text and have the text wrap around the image, float is the ideal tool. We used to use float to build layouts, but shouldn't anymore because we now have Flexbox and CSS Grids to help create solid, multi-column responsive sites.

Floating removes an element from the normal flow of HTML elements and places it on the left or right side of its container or nearest element.

```css
.float {
  background: lightblue;
  padding: 30px;
  margin: 10px;
}

.floated-right {
  float: right;
}

.floated-left {
  float: left;
}
```

```html
<div>
  <div class="float floated-right">Floated</div>
  <h2>Float right</h2>
  <p>The image has been floated to the right side of the text.</p>
</div>

<div>
  <div class="float floated-left">Floated</div>
  <h2>Float left</h2>
  <p>The image has been floated to the right side of the text.</p>
</div>
```

## Demo 2: clear

```css
.float {
  margin: 10px;
  float: right;
  width: 300px;
}

.clear {
  clear: right;
}
```

```html
<div>
  <img
    src="https://images.unsplash.com/photo-1489417139533-915815598d31"
    class="float"
  />
  <h2>Dogs</h2>
  <p>
    The domestic dog (Canis lupus familiaris when considered a subspecies of the
    gray wolf or Canis familiaris when considered a distinct species).
  </p>

  <h2 class="clear">Cats</h2>
  <p class="clear">
    The domestic cat (Felis silvestris catus or Felis catus) is a small,
    typically furry, carnivorous mammal. They are often called house cats when
    kept as indoor pets or simply cats when there is no need to distinguish them
    from other felids and felines. They are often valued by humans for
    companionship and for their ability to hunt vermin. There are more than
    seventy cat breeds recognized by various cat registries.
  </p>
</div>

<i
  >Content used under the Creative Commons Attribution-ShareAlike License from
  Wikipedia</i
>
```

## Demo 3: Clearfix

### A problem

```css
.float {
  margin: 10px;
  float: right;
  height: 150px;
}

.clear {
  clear: right;
}

div {
  border: 1px solid black;
}
```

```html
<div>
  <img
    src="https://images.unsplash.com/photo-1489417139533-915815598d31"
    class="float"
  />
  <h2>Dogs</h2>
  <p>
    The domestic dog (Canis lupus familiaris when considered a subspecies of the
    gray wolf or Canis familiaris when considered a distinct species).
  </p>
</div>
<br /><br />
```

### A Fix

To help solve this issue, developers created a workaround called clearfix. We create a pseudo-element '::after', which goes at the end of the div. We then clear it to force the container to adjust to the height of the floated element.

```css
.float {
  margin: 10px;
  float: right;
  height: 150px;
}

.clear {
  clear: right;
}

div {
  border: 1px solid black;
}

.clearfix::after {
  clear: both;
  content: '';
  display: table;
}
```

```html
<div class="clearfix">
  <img
    src="https://images.unsplash.com/photo-1489417139533-915815598d31"
    class="float"
  />
  <h2>Dogs</h2>
  <p>
    The domestic dog (Canis lupus familiaris when considered a subspecies of the
    gray wolf or Canis familiaris when considered a distinct species).
  </p>
</div>

<br /><br />
```

## Position

### Static

Static position is the default behavior.

### Relative

```css
.relative-position {
  position: relative;
  top: 30px;
  left: 30px;
  background: lightblue;
  padding: 10px;
}
.container {
  height: 150px;
}
```

```html
<div class="container">
  <p>
    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Ut ac neque
    aliquam, semper massa nec, viverra odio. Donec sed pretium lectus. Maecenas
    dapibus non purus non auctor.
  </p>
  <div class="relative-position">Relative positioned content</div>
</div>
```

### Absolute

```css
.absolute-position {
  position: absolute;
  top: 30px;
  left: 30px;
  background: lightblue;
  padding: 10px;
}

.container {
  position: relative;
  height: 150px;
}
```

```html
<div class="container">
  <p>
    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Ut ac neque
    aliquam, semper massa nec, viverra odio. Donec sed pretium lectus. Maecenas
    dapibus non purus non auctor.
  </p>
  <div class="absolute-position">Absolute positioned content</div>
</div>
```

### Fixed

```css
.fixed-position {
  position: fixed;
  top: 30px;
  left: 30px;
  background: lightblue;
  padding: 10px;
}
```

```html
<div class="container">
  <p>
    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Ut ac neque
    aliquam, semper massa nec, viverra odio. Donec sed pretium lectus. Maecenas
    dapibus non purus non auctor.
  </p>
  <p>
    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Ut ac neque
    aliquam, semper massa nec, viverra odio. Donec sed pretium lectus. Maecenas
    dapibus non purus non auctor.
  </p>
  <p>
    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Ut ac neque
    aliquam, semper massa nec, viverra odio. Donec sed pretium lectus. Maecenas
    dapibus non purus non auctor.
  </p>
  <p>
    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Ut ac neque
    aliquam, semper massa nec, viverra odio. Donec sed pretium lectus. Maecenas
    dapibus non purus non auctor.
  </p>
  <p>
    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Ut ac neque
    aliquam, semper massa nec, viverra odio. Donec sed pretium lectus. Maecenas
    dapibus non purus non auctor.
  </p>
  <div class="fixed-position">Fixed positioned content</div>
</div>
```

### Sticky

```css
.sticky-position {
  position: sticky;
  top: 20px;
  background: lightblue;
  padding: 10px;
}

.container {
  height: 500px;
}
```

```html
<div class="container">
  <p>
    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Ut ac neque
    aliquam, semper massa nec, viverra odio. Donec sed pretium lectus. Maecenas
    dapibus non purus non auctor.
  </p>
  <div class="sticky-position">Sticky positioned content</div>
  <p>
    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Ut ac neque
    aliquam, semper massa nec, viverra odio. Donec sed pretium lectus. Maecenas
    dapibus non purus non auctor.
  </p>
  <p>
    Quisque et mi sed lectus molestie porttitor et nec orci. Praesent non
    maximus enim. Aenean fermentum elementum orci ut lacinia. Curabitur rutrum
    vestibulum elit, vel vehicula nisl sagittis in. Curabitur facilisis nec diam
    eget consequat.
  </p>
  <p>
    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Ut ac neque
    aliquam, semper massa nec, viverra odio. Donec sed pretium lectus. Maecenas
    dapibus non purus non auctor.
  </p>
  <p>
    Quisque et mi sed lectus molestie porttitor et nec orci. Praesent non
    maximus enim. Aenean fermentum elementum orci ut lacinia. Curabitur rutrum
    vestibulum elit, vel vehicula nisl sagittis in. Curabitur facilisis nec diam
    eget consequat.
  </p>
  <p>
    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Ut ac neque
    aliquam, semper massa nec, viverra odio. Donec sed pretium lectus. Maecenas
    dapibus non purus non auctor.
  </p>
  <p>
    Quisque et mi sed lectus molestie porttitor et nec orci. Praesent non
    maximus enim. Aenean fermentum elementum orci ut lacinia. Curabitur rutrum
    vestibulum elit, vel vehicula nisl sagittis in. Curabitur facilisis nec diam
    eget consequat.
  </p>
  <p>
    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Ut ac neque
    aliquam, semper massa nec, viverra odio. Donec sed pretium lectus. Maecenas
    dapibus non purus non auctor.
  </p>
  <p>
    Quisque et mi sed lectus molestie porttitor et nec orci. Praesent non
    maximus enim. Aenean fermentum elementum orci ut lacinia. Curabitur rutrum
    vestibulum elit, vel vehicula nisl sagittis in. Curabitur facilisis nec diam
    eget consequat.
  </p>
</div>
```

## z-index

With positioning, it’s easy to get elements on top of one another. To determine the order in which elements stack up, we can use z-index. Z-index is fairly simple to use; the higher the z-index number, the higher in the order it goes.

```css
.one {
  z-index: 2;
  background: lightblue;
  padding: 20px;
  width: 200px;
  position: relative;
}

.two {
  z-index: 1;
  background: lightgreen;
  padding: 20px;
  width: 200px;
  position: absolute;
  top: 40px;
  left: 40px;
}

.container {
  position: relative;
  height: 100px;
}
```

```html
<div class="container">
  <div class="one">Block One</div>
  <div class="two">Block Two</div>
</div>
```
