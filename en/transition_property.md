TOPICS: transition property
        transition-property property
        transition-duration property
        transition-timing-function property
        transition-delay property

# CSS Transition Property: `transition`

The **`transition`** CSS property is a shorthand property for **`transition-property`**,
**`transition-duration`**, **`transition-timing-function`** and **`transition-delay`**.

Transitions enable you to define the transition between two states of an element. Different states
may be defined using pseudo-classes like [`:hover`](/en/webfrontend/:hover) or [`:active`](/en/webfrontend/:active)
or dynamically set using JavaScript.

The `transition` property is specified as one or more single-property transitions, separated by commas.
extra transition descriptions beyond the number of properties actually being animated are ignored.

## CSS The Name Of The Transition Property `transition-property`

**`transition-property`** specifies the name of the application **transition property**.

!!! warn "Note"
    The set of properties that can be animated is subject to change. As such, you should avoid
    including any properties in the list that don't currently animate, as someday they might,
    causing unexpected results.
    If you specify a shorthand property (e.g., `background`), all of its longhand sub-properties
    that can be animated will be.

| Property value | Description |
| :--- | :--- |
| **`none`** | No propertys will get the transition effect |
| **`all`** | All propertys will get a transition effect |
| **property** | Defines a list of CSS property names for applying transition effects, separated by commas |
| **ident** | The property name. From lowercase letters `a` to `z`, numbers `0` to `9`, underscores (`_`) and dashes (`-`). The first non-dash character cannot be a number. Also, you cannot start with two dashes |

## CSS Transition Duration Property `transition-duration`

The **`transition-duration`** property is specified in units of **seconds** or **milliseconds**
**time required for transition animation**. The default value is `0s`, which means no transition
animation occurs.

| Property value | Description |
| :--- | :--- |
| **time** | Specifies **the time it takes to complete the transition effect** (in **seconds** or **milliseconds**). The default value is `0`, meaning no effect |

## CSS Transition Time Series Function Properties `transition-timing-function`

The CSS **`transition-timing-function`** property is used to describe how this intermediate value
is calculated. In essence, an acceleration curve will be established by this function, so the speed
of change can continuously change during the entire `transition` process.

This acceleration curve is defined by the timing function and then acts on the transition of each
CSS property.

| Property value | Description |
| :--- | :--- |
| **`linear`** | Specifies the transition effect **starting to the end at the same speed** (equal to `cubic-bezier (0,0,1,1)`) |
| **`ease`** | Provision **slow start**, then **get faster**, then **slow end** transition effect (equal to `cubic-bezier (0.25,0.1,0.25,1)`) |
| **`ease-in`** | Specifies the transition effect **slow start** (equal to `cubic-bezier (0.42,0,1,1)`) |
| **`ease-out`** | Specifies the transition effect with **slow end** (equal to `cubic-bezier (0,0,0.58,1)`) |
| **`ease-in-out`** | Specifies the transition effect of **slow start** and **end** (equal to `cubic-bezier (0.42,0,0.58,1)`) |
| **`cubic-bezier(n,n,n,n)`** | Defined in `cubic-bezier` function **own value**. Possible values are values between `0` and `1` |

## CSS Transition Start Wait Time Property `transition-delay`

The CSS **`transition-delay`** property specifies the time to wait before the transition effect
**starts to take effect**. The value is in units of **seconds** (`s`) or **milliseconds** (`ms`),
indicating when the animation transition effect will start.

| Property value | Description |
| :--- | :--- |
| **time** | Wait **seconds** or **milliseconds** to wait for the switching effect to start |

## Examples

```css
div {
  width: 100px;
  height: 100px;
  background: red;
  transition-property: width; /* Specify width as the transition property */
  transition-duration: 2s; /* The transition animation is completed in 2s */
  transition-timing-function: ease-in; /* The transition animation starts at a slow speed */
  transition-delay: 1s; /* Wait for one second to execute the transition animation */

  /* The following is a shorthand */
  /* transition: width 5s ease-in 1s; */
}

div:hover {
  width:300px;
}
```

```html
<div></div>
<p>Move the mouse over the block to see the transition animation effect.</p>
```
