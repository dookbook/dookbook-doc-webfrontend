TOPICS: CSS Animation
        animation property
        animation-name property
        animation-duration property
        animation-timing-function property
        animation-delay property
        animation-iteration-count property
        animation-direction property
        animation-fill-mode property
        animation-play-state property
        @keyframes property

# CSS Animation （`animation`）

CSS3 can create **animations**, which can replace many **webpage animated images**, Flash animations,
and JavaScript effects.

Animated properties can gradually change from one value to another, such as **size**, **number**,
**percent**, and **color**.

## CSS3 `@keyframes` Rules

**`@keyframes`** The rule is to create animation. Specify a CSS style and animation that will
gradually change from **current style** to **new style**

Use **%** when the specified change occurs, or the keywords "**from**" and "**to**", which are the
same as **0%** to **100%**.

**0%** is the opening animation, **100%** is when the animation is complete.

## CSS3 Animation Property

| Property | Description |
| :--- | :--- |
| **`animation`** | **shorthand property** for all animation properties, except for the **`animation-play-state`** property. |
| **`animation-name`** | Specifies **a series of animations to be applied**, each name representing an animation sequence defined by **`@keyframes`** .|
| **`animation-duration`** | Specify **the duration of an animation cycle**. The default value is `0s`, which means no animation. |
| **`animation-timing-function`** | Specify the CSS animation in each animation cycle **rhythm of execution**. |
| **`animation-delay`** | Specify the animation **when to start**. The default is `0`.The default is `0`. Negative values are allowed, if: -2s makes the animation start immediately, but skips 2 seconds to enter the animation. |
| **`animation-iteration-count`** | Specifies **the number of times the animation runs before it ends**, which can be **1** or **infinite loop**. |
| **`animation-direction`** | Specifies **whether the animation should be played in reverse**. |
| **`animation-fill-mode`** | Specifies how the animation applies styles to its target **before** and **after** execution. |
| **`animation-play-state`** | Specifies whether the animation is **running** or **paused**. |

## `animation-name` Property Value

| Property Value | Description |
| :--- | :--- |
| **keyframename** | Specifies the name of the **keyframe to bind to the selector**. |
| **`none`** | Specifies whether there is animation (can be used to override the animation from the cascade). |

## `animation-duration` Property Value

| Property Value | Description |
| :--- | :--- |
| **time** | Specify the animation **time taken for playback completion**. The default value is `0`, which means no animation effect. |

## `animation-timing-function` Property Value

| Property Value | Description |
| :--- | :--- |
| **`linear`** | Animation from beginning to end **speed is the same**. |
| **`ease`** | Default. Animation starts at **low speed**, then **speeds up**, and **slows before it ends**. |
| **`ease-in`** | Animation starts at **low speed**. |
| **`ease-out`** | Animation ends at **low speed**. |
| **`ease-in-out`** | Animation starts at **low speed** and **ends at**. |
| **`cubic-bezier(n,n,n,n)`** | Your own value in the `cubic-bezier` function. Possible values are values from `0` to `1`. |

## `animation-delay` Property Value

| Property Value | Description |
| :--- | :--- |
| **time** | Optional. Define the animation **time to wait before starting**, in **seconds** or **milliseconds**. The default value is `0` .|

## `animation-iteration-count` Property Value

| Property Value | Description |
| :--- | :--- |
| **n** | **A number**, definition **how many animations should be played** .|
| **`infinite`** | Specifies that the animation should play **indefinitely** (forever). |

## `animation-direction` Property Value

!!! warn "Note"
    If the animation is set to play only once, this property will have no effect.

| Property Value | Description |
| :--- | :--- |
| **`normal`** | Defaults. Animation press **Normal Play**. |
| **`reverse`** | Animation **Reverse Play**. |
| **`alternate`** | The animation plays **forward in odd times (1, 3, 5 ...)** and **backwards in even times (2, 4, 6, ...)**. |
| **`alternate-reverse`** | The animation is played **backward in odd times (1, 3, 5 ...)** and **forward in even times (2, 4, 6, ...)** .|

## `animation-fill-mode` Property Value

| Property Value | Description |
| :--- | :--- |
| **`none`** | Defaults. The animation does not apply any style to the target element before and after the animation is executed. |
| **`forwards`** | The target retains the value calculated from the last keyframe encountered during execution. The last keyframe depends on the values of *`animation-direction`* and *`animation-iteration-count`*. |
| **`backwards`** | The animation will immediately apply the value defined in the first keyframe when applied to the target, and retain this value during *`animation-delay`*. The first keyframe depends on the value of *`animation-direction`*. |
| **`both`** | Animation follows the rules of *`forwards`* and *`backwards`*. That is, the animation expands the animation properties in both directions. |

## `animation-play-state` Property Value

| Property Value | Description |
| :--- | :--- |
| **`paused`** | Current animation to be stopped. |
| **`running`** | The current animation is running. |

## Example

```css
div {
  width: 100px;
  height: 100px;
  background: red;
  position: relative;
  animation-name: mymove; /* Bind @keyframes to the name of mymove */
  animation-duration: 2s; /* Animation completed in two seconds */
  animation-timing-function: linear; /* Play the animation at a constant speed */
  animation-delay: 3s; /* Wait for 3s to start the animation */
  animation-iteration-count: 2; /* The animation will be executed twice */
  animation-direction: alternate; /* Play in odd forward direction, even in reverse */
  animation-fill-mode: forwards; /* Will stay on the first frame, depending on the values of the animation-iteration-count and animation-direction properties */
  animation-play-state: running; /* Allow animation to execute */
}

/* Shorthand example, equivalent to the above code */
div {
  width: 100px;
  height: 100px;
  background: red;
  position: relative;
  animation: mymove 2s linear 3s 2 alternate forwards;
  animation-play-state: running;
}

/* Animation evolution process */
@keyframes mymove {
  from { left: 0; }
  to { left: 200px; }
}
```
