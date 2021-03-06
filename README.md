Swipe [![Code Climate](https://codeclimate.com/github/lyfeyaj/swipe/badges/gpa.svg)](https://codeclimate.com/github/lyfeyaj/swipe)
=====

Swipe is the most accurate touch slider and extremely lightweight (only 5kb for minified version)

## Note

Swipe is originally created by **[Brad Birdsall](https://github.com/thebird)** which didn't update for a really long time, and this version is maintain by **[Felix Liu](https://github.com/lyfeyaj)** with new features and bugfix.

## Usage

You can directly install this package via Bower: `bower install swipe-js`

See [online example](http://lyfeyaj.github.io/swipe/)

Swipe only needs to follow a simple pattern. Here is an example:

``` html
<div id='slider' class='swipe'>
  <div class='swipe-wrap'>
    <div></div>
    <div></div>
    <div></div>
  </div>
</div>
```

Above is the initial required structure– a series of elements wrapped in two containers. Place any content you want within the items. The containing div will need to be passed to the Swipe function like so:

``` js
window.mySwipe = new Swipe(document.getElementById('slider'));
```

I always place this at the bottom of the page, externally, to verify the page is ready.

Also Swipe needs just a few styles added to your stylesheet:

``` css
.swipe {
  overflow: hidden;
  visibility: hidden;
  position: relative;
}
.swipe-wrap {
  overflow: hidden;
  position: relative;
}
.swipe-wrap > div {
  float:left;
  width:100%;
  position: relative;
}
```

## Config Options

Swipe can take an optional second parameter– an object of key/value settings:

- **startSlide** Integer *(default:0)* - index position Swipe should start at

-	**speed** Integer *(default:300)* - speed of prev and next transitions in milliseconds.

- **auto** Integer - begin with auto slideshow (time in milliseconds between slides)

- **continuous** Boolean *(default:true)* - create an infinite feel with no endpoints

- **autoRestart** Boolean *(default:true)* - auto restart slideshow after user's touch event or next/prev calls

- **disableScroll** Boolean *(default:false)* - stop any touches on this container from scrolling the page

- **stopPropagation** Boolean *(default:false)* - stop event propagation
 
-	**callback** Function - runs at slide change.

- **transitionEnd** Function - runs at the end slide transition.

### Example

``` js

window.mySwipe = new Swipe(document.getElementById('slider'), {
  startSlide: 0,
  speed: 400,
  auto: 3000,
  continuous: true,
  disableScroll: false,
  stopPropagation: false,
  callback: function(index, elem) {},
  transitionEnd: function(index, elem) {}
});

```

## Swipe API

Swipe exposes a few functions that can be useful for script control of your slider.

`prev()` slide to prev

`next()` slide to next

`getPos()` returns current slide index position

`getNumSlides()` returns the total amount of slides

`slide(index, duration)` slide to set index position (duration: speed of transition in milliseconds)

`restart() restart the auto slide`

`stop() stop the auto slide`

`kill() remove swipe totally`

## Browser Support
Swipe is now compatible with all browsers, including IE7+. Swipe works best on devices that support CSS transforms and touch, but can be used without these as well. A few helper methods determine touch and CSS transition support and choose the proper animation methods accordingly.

## Who's using Swipe

<img src='icons/cnn.png' width='170' height='80'>
<img src='icons/airbnb.png' width='170' height='80'>
<img src='icons/nhl.png' width='170' height='80'>
<img src='icons/htc.png' width='170' height='80'>
<img src='icons/thinkgeek.png' width='170' height='80'>
<img src='icons/snapguide.png' width='170' height='80'>

Shoot me a [note](mailto:lyfeyaj@gmail.com) if you want your logo here

## License
Copyright (c) 2015 Brad Birdsall and Felix Liu Licensed under the [The MIT License (MIT)](http://opensource.org/licenses/MIT).
