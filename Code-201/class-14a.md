# Read 14a - Notes: CSS Transforms, Transitions, and Animations

### [Transforms](https://learn.shayhowe.com/advanced-html-css/css-transforms/)

+ Transform properties come in two different settings: two-dimensional and three dimensional. Each of these come with their own individual properties and values

+ For the best support, vendor prefixes are encouraged, but may need the nightly version of [Chrome](https://tools.google.com/dlpage/chromesxs/) to see everything.

+ **General syntax**: transform type followed by a specific amount inside parenthesis:
```
div {
  -webkit-transform: scale(1.5);
     -moz-transform: scale(1.5);
       -o-transform: scale(1.5);
          transform: scale(1.5);
}
```

**Note: code examples from here on out use generic "transform" for simplicity, but when actually coding, use the vendor prefixes as shown above to ensure expected outcome**

### 2-D transforms

+ 2-D transforms work on the x and y axes. (3-D transforms work on the x, y, and z-xis)

+ **2D Rotate**: provides the ability to rotate an element from 0 to 360 degrees. 
  - Positive value rotates clockwise, negative value rotates counter-clockwise. 
  - The default piont of rotation is the center of the element (50% 50% for both x and y axis)
```
.box-1 {
  transform: rotate(20deg);
}
.box-2 {
  transform: rotate(-55deg);
}
```
+ **2D Scale**: provides the ability to change the appeared size of an element. 
  - The default scale value is 1 (.01 to .99 makes it smaller, 1.01+ makes it bigger)
  - It is possible to scale only the height or width of an element using *scaleX* and *scaleY* values. They can be set simultaneously to different sizes; x-axis value goes first followed by y-axis value.
```
.box-1 {
  transform: scale(.75);
}
.box-2 {
  transform: scale(1.25);
}
.box-1 {
  transform: scaleX(.5);
}
.box-2 {
  transform: scaleY(1.15);
}
.box-3 {
  transform: scale(.5, 1.15);
}
```
+ **2D Translate**: works a bit like relativer positioning, pushing and pulling an element in different directions without interrrupting the nromal flow of the document.
  - *translateX* changes position in the x-axis, *translateY* changes position in the y-axis
  - both values can be set simultaneously; x value first then y value
  - distance values used maybe general length, most commonly pixels or percentages. Positive values push an element down and to the right; negative values pull an element up and to the left of its defualt position

```
  .box-1 {
  transform: translateX(-10px);
}
.box-2 {
  transform: translateY(25%);
}
.box-3 {
  transform: translate(-10px, 25%);
}
```

+ **2D Skew**: used to distort elements on the x-axis, y-axis, or both.
  - *skewX* distorts on the x-axis; *skewY* distorts on the y-axis. 
  - both axese can be skewed, x value first then y value
  - the distance calculation of skew is measured in **units of degrees**.

```
.box-1 {
  transform: skewX(5deg);
}
.box-2 {
  transform: skewY(-20deg);
}
.box-3 {
  transform: skew(5deg, -20deg);
}
```

### Combining transforms
+ It is common to combine transforms to be used at once.

+ To combine, list the tranform values within the transform property one after the other **without the use of commas**.
```
.box-1 {
  transform: rotate(25deg) scale(.75);
}
.box-2 {
  transform: skew(10deg, 20deg) translateX(20px);
}
```
+ For a [deep dive](https://dev.opera.com/articles/view/understanding-the-css-transforms-matrix/) into matrix property reveals the math behind transforms.

**Sample code for a 2D cube**
```
.cube {
  position: relative;
}
.side {
  height: 95px;
  position: absolute;
  width: 95px;
}
.top {
  background: #9acc53;
  transform: rotate(-45deg) skew(15deg, 15deg);
}
.left {
  background: #8ec63f;
  transform: rotate(15deg) skew(15deg, 15deg) translate(-50%, 100%);
}
.right {
  background: #80b239;
  transform: rotate(-15deg) skew(-15deg, -15deg) translate(50%, 100%);
}
```
### Transform Origin

+ Default is center (50% x-axis, 50% y-axis)

+ Accepts 2 values but when only one is entered, it is used for both x and y-axis.

+ 0 0 = top left; 100% 100% = bottom right; 20px 50px = sets origin at 20px across and 50 px down an element.

+ Issues can arise when using `tranform-origin` in conjunction with `translate` transform value.

### Perspective
+ Perspectives are useful for 3D transforms; think of them as *vanishing points*.

+ It can be used in two ways:
  - using `perspective` value withikn the `trnasform ` property on individual elements
  - using `perspective` property on the parent element of the child elements being transformed
```
.box {
  transform: perspective(200px) rotateX(45deg);
}
```

+ **Perspective depth value**: can be set as `none` or length measurement. 
  - higher the value, the further away the perspective === low intensity perspective
  - lower the value, the closer the perspective === high intensity perspective

+ **Perspective origin**: same concept as `transform-origin` property.
  - origin of a perspective identifies the coordinates of the vanishing point of a transform

### 3D Transforms

+ **3D Rotate**: used to rotate on x, y, or z-axis. 
  - uses `rotateX`, `rotateY`, and `rotateZ`
  - positive values will rotate the element clockwise, and negative values will rotate the element counterclockwise

+ **3D Scale**: useful only when more than 1 dimensional transforms are working together; otherwise, the element will appear unchanged.

+ **3D Translate**: negative values push an element further away on the z-axis, resulting in a smaller element. Positive values have opposite effect, resulting in a larger element.

+ **3D Skew**: elements cannot be skewed on z-axis so this does not work in 3D.

### Transform Style

+ To allow nested elements to transform in their own three-dimensional plane use the `transform-style` property with the preserve-3d value.

+ The `transform-style` property needs to be placed on the parent element, above any nested transforms.

+ The `preserve-3d` value allows the transformed children elements to appear in their own 3D plane while the `flat` value forces the transformed children elements to lie flat on the 2D plane (see example from [reference website](https://webkit.org/blog-files/3d-transforms/transform-style.html))

### Backface Visibility

+ If you want to hide elements from being seen from the back (e.g. when used with `rotateY(180deg)` value), set the `backface-visibility` property to `hidden`.

+ The default value for `backface-visibility` is `visible`. See this [additional reference](https://css-tricks.com/almanac/properties/b/backface-visibility/) on this topic.

+ **NOTE: See 3D cube demo for a good reference of how 3D transforms are used together to create a rotating 3D box effect.**

*****
## [Transitions & Animations](https://learn.shayhowe.com/advanced-html-css/transitions-animations/)

### Transitions
In order for a transition to take place, an element **must have a changed state**, and different styles must be identified for **each state**. 
  - best way to implement chnaged states are using pseudo-classes: `:hover`, `:focus`, `:active`, and `:target`
  - see [additional reference](https://alistapart.com/article/understanding-css3-transitions/) on transitions

+ In the example below the box will change its background color over the course of 1 second in a linear fashion.
```
.box {
  background: #2db34a;
  transition-property: background;
  transition-duration: 1s;
  transition-timing-function: linear;
}
.box:hover {
  background: #ff7b29;
}
```
+ Same effect as above using vendor prefix (should be used, left out for simplicity for all examples here) 
```
.box {
    background: #2db34a;
    -webkit-transition-property: background;
       -moz-transition-property: background;
         -o-transition-property: background;
            transition-property: background;
    -webkit-transition-duration: 1s;
       -moz-transition-duration: 1s;
         -o-transition-duration: 1s;
            transition-duration: 1s;
    -webkit-transition-timing-function: linear;
       -moz-transition-timing-function: linear;
         -o-transition-timing-function: linear;
            transition-timing-function: linear;
}
.box:hover {
  background: #ff7b29;
}
```

### Transition Property
+ `transition-property` determines exactly waht properties will be altered in conjunction with th eother transitional properties.

+ If multiple properties need to be transitioned they may be comma separated within the `transition-property` value. Additionally, the keyword value `all` may be used to transition all properties of an element.
```
.box {
    background: #2db34a;
    border-radius: 6px
    transition-property: background, border-radius;
    transition-duration: 1s;
    transition-timing-function: linear;
  }
  .box:hover {
    background: #ff7b29;
    border-radius: 50%;
  }
```

+ **Not all properties may be transitioned**, only properties that have an identifiable halfway point. For example, the `display` property cannot be transitioned. (see reference link for common examples)

### Transition Duration

+ `transition-duration` sets the duration in which a transition takes place. It uses general timing values (e.g. seconds (s) or milliseconds (ms); can also use fractional measurements (.2s).

+ When transitioning multiple properties, you can set multiple durations, one for each property.  It is declared using comma separated values **(note: order matters)**.

+ If only one value is declared, the single value will be applied to all the properties being transitioned.

```
.box {
  background: #2db34a;
  border-radius: 6px;
  transition-property: background, border-radius;
  transition-duration: .2s, 1s;
  transition-timing-function: linear;
}
.box:hover {
  background: #ff7b29;
  border-radius: 50%;
}
```

### Transition Timing
+ `transition-timing-function` property is used to set the speed in which a transition will move. It allows multiple speeds within a single duration. Popular keyword values include:
  - `linear`
  - `ease-in`
  - `ease-out`
  - `ease-in-out`
  - The linear keyword value identifies a transition moving in a constant speed from one state to another. The ease-in value identifies a transition that starts slowly and speeds up throughout the transition, while the ease-out value identifies a transition that starts quickly and slows down throughout the transition. The ease-in-out value identifies a transition that starts slowly, speeds up in the middle, then slows down again before ending.

 Applying this to the example from the transition duration:
 ```
 .box {
  background: #2db34a;
  border-radius: 6px;
  transition-property: background, border-radius;
  transition-duration: .2s, 1s;
  transition-timing-function: linear, ease-in;
}
.box:hover {
  background: #ff7b29;
  border-radius: 50%;
}
```

### Transition Delay
+ `transition-delay` sets a time value, seconds or milliseconds, that determines how long a transition should be stalled before executing. 
+ Multiple delays are declared as comma separated values
+ Using the previous examples from this section:
```
.box {
  background: #2db34a;
  border-radius: 6px
  transition-property: background, border-radius;
  transition-duration: .2s, 1s;
  transition-timing-function: linear, ease-in;
  transition-delay: 0s, 1s;
}
.box:hover {
  background: #ff7b29;
  border-radius: 50%;
}
```

### Shorthand Transitions
+ a shorthand property, `transition`, capable of supporting all of these different properties and values. 

+ Using the `transition` value alone, you can set every transition value in the order of `transition-property`, `transition-duration`, `transition-timing-function`, and lastly `transition-delay`. Do not use commas with these values unless you are identifying numerous transitions.

+ To set numerous transitions at once, set each individual group of transition values, then use a comma to separate each additional group of transition values.
```
.box {
  background: #2db34a;
  border-radius: 6px;
  transition: background .2s linear, border-radius 1s ease-in 1s;
}
.box:hover {
  color: #ff7b29;
  border-radius: 50%;
}
```
+ Transition examples from the reference site (note: sample code is avaialble):
  - transitional buttons
  - card flip
  
## Animations (see also [this reference](https://www.smashingmagazine.com/2011/09/the-guide-to-css-animation-principles-and-examples/))
Animations allow multipe state (changes) transitions. 

+ To set multiple points at which an element should undergo a transition, use the `@keyframes` rule, which includes:
  - animation name
  - any animation breakpoints
  - the properties intended to be animated

+ ** Note: the `@keyframes` rule must be vendor prefixed.
  - `@-moz-keyframes`
  - `@-webkit-keyframes`
  - `@-o-keyframes`

+ As with transitions only individual properties may be animated.

### Animation Name

+ Once the keyframes for an animation have been declared they need to be assigned to an element. 
  - the `animation-name` property is used with the animation name, identified from the @keyframes rule, as the property value. 
  - `animation-name` declaration is applied to the element in which the animation is to be applied to.
  - also need to declare an `animation-duration` property and value so that the browser knows how long an animation should take to complete.

### Animation Duration, Timing Function, and Delay

+ Once you have declared the `animation-name` property on an element, animations behave similarly to transitions. 

+ A timing function and delay can be declared using the `animation-timing-function` and `animation-delay` properties respectively.

```
.stage:hover .ball {
  animation-name: slide;
  animation-duration: 2s;
  animation-timing-function: ease-in-out;
  animation-delay: .5s;
}
```
## Customizing Animations

### Animation Iteration

+ By default, animations run their cycle once from beginning to end and then stop.

+ To have an animation repeat itself numerous times the `animation-iteration-count` property may be used. Values for the `animation-iteration-count` property include either **an integer** or the `infinite` keyword.
```
.stage:hover .ball {
  animation-name: slide;
  animation-duration: 2s;
  animation-timing-function: ease-in-out;
  animation-delay: .5s;
  animation-iteration-count: infinite;
}
```

### Animation Direction
+ Declare the direction an animation completes using the `animation-direction` property. Values for the animation-direction property include `normal`, `reverse`, `alternate`, and `alternate-reverse`.

+ Using the `animation-iteration-count` property may limit the number of times an animation runs both forwards and backwards. 

+ The count starts at 1 running an animation forwards from 0% to 100%, then adds 1 running an animation backwards from 100% to 0%. Combining for a total of 2 iterations. 

+ The `alternate` value also inverses any timing functions when playing in reverse. If an animation uses the ease-in value going from 0% to 100%, it then uses the ease-out value going from 100% to 0%.

+ Movement directions:
  - the `normal` value plays an animation as intended from beginning to end. 
  - the `reverse` value will play the animation exactly opposite as identified within the @keyframes rule, thus starting at 100% and working backwards to 0%.
  - the `alternate` value will play an animation forwards then backwards. 
  - the `alternate-reverse` value combines both the alternate and reverse values, running an animation backwards then forwards.
```
.stage:hover .ball {
  animation-name: slide;
  animation-duration: 2s;
  animation-timing-function: ease-in-out;
  animation-delay: .5s;
  animation-iteration-count: infinite;
  animation-direction: alternate;
}
```
### Animation Play State

+ `animation-play-state` property allows an animation to be played or paused using the `running` and `paused` keyword values respectively. 

+ When you play a paused animation, it will resume running from its current state rather than starting from the very beginning again.

+ In the example below the animation-play-state property is set to paused when making the stage active by clicking on it. Notice how the animation will temporarily pause until you let up on the mouse.
```
.stage:hover .ball {
  animation-name: slide;
  animation-duration: 2s;
  animation-timing-function: ease-in-out;
  animation-delay: .5s;
  animation-iteration-count: infinite;
  animation-direction: alternate;
}
.stage:active .ball {
  animation-play-state: paused;
}
```

### Animation Fill Mode

+ `animation-fill-mode` property identifies how an element should be styled either before, after, or before and after an animation is run. 

+ The `animation-fill-mode` property accepts four keyword values: `none`, `forwards`, `backwards`, and `both`.

+ Behaviors of this property:
  - `none` value will not apply any styles to an element before or after an animation has been run.
  - `forwards` value will keep the styles declared within the last specified keyframe. These styles may, however, be affected by the `animation-direction` and `animation-iteration-count` property values, changing exactly where an animation ends.
  - The `backwards` value will apply the styles within the first specified keyframe as soon as being identified, before the animation has been run. This does include applying those styles during any time that may be set within an animation delay. The backwards value may also be affected by the `animation-direction` property value.
  - the `both` value will apply the behaviors from both the `forwards` and `backwards` values.

```
.stage:hover .ball {
  animation-name: slide;
  animation-duration: 2s;
  animation-timing-function: ease-in-out;
  animation-delay: .5s;
  animation-fill-mode: forwards;
}
.stage:active .ball {
  animation-play-state: paused;
}
```
## Shorthand Animations

+ Animations can be written out in shorthand format; accomplished using one `animation` property rather than multiple.

+ The order of values within the `animation` property should be the following:
  1. `animation-name`
  2. `animation-duration`
  3. `animation-timing-function`
  4. `animation-delay`
  5. `animation-iteration-count`
  6. `animation-direction`
  7. `animation-fill-mode`
  8. `animation-play-state`

+ See additional [animation reference](The order of values within the animation property should be animation-name, animation-duration, animation-timing-function, animation-delay, animation-iteration-count, animation-direction, animation-fill-mode, and lastly animation-play-state.).

```
.stage:hover .ball {
  animation: slide 2s ease-in-out .5s infinite alternate;
}
.stage:active .ball {
  animation-play-state: paused;
}
```
*****
## Article: [8 SIMPLE CSS3 TRANSITIONS THAT WILL WOW YOUR USERS](http://www.webdesignerdepot.com/2014/05/8-simple-css3-transitions-that-will-wow-your-users/)

See the article link for sample code and the transitions in action:

1. Fade in
2. Change color
3. Grow and shrink
4. Rotate elements
5. Square to circle
6. 3D Shadow
7. Swing
8. Inset border

*****
## Additional Code-Pen samples of transition examples

1. [6 buttons animated](https://codepen.io/retyui/pen/ByoaXV)
2. [CSS Keyframes animation](https://codepen.io/akshaychauhan/pen/oAfae)
3. [404](https://codepen.io/kieranfivestars/pen/MYdQxX)
4. [Pure CSS bounce animation](https://codepen.io/dp_lewis/pen/gCfBv)


*****
[<<< Back to Main](https://sangmlee76.github.io/reading-notes/)