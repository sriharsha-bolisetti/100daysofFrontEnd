###### Forcing Inheritance
- Occasionally, you may wish to have a property inherit even when it woulnd't normally do so.
- A good example is link colors. By default, anchor tags have built-in styles that give unvisited, inactive links a blue hue
- The trouble is even though `color` is an inheritable property, `it's being overwritten by the default style, color: -webkit-link`
- We can fix this by explicitly telling anchor tags to inherit their containing text color:
```
a {
    color:inherit;
}
```
##### The Box Model
1. Content
2. Padding
3. Border
4. Margin

- The `box-sizing` CSS property allows us to change the rules for size calculations. 
- The default value `content-box` only takes inner content into account, but it offers an alternative value: `border-box`
- With `box-sizing: border-box`, things behave `much` more intuitively.
- `margin has no effect on dimensions`, no matter the box-sizing.
- Percentage-based widths and heights are relative to the amount of space being made available by the parent.
- `border-radius should have been corner-radius`
- border vs outline -> `outline doesn't affect layout`
- Outline is kinda more like box-shadow; it's a cosmetic effect draped over an element, without nudging it around, or changing its size.
- Outlines are stacked outside border, and can sometimes be used as a `second border`, for effect
