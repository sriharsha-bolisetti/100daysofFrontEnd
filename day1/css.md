- A rule, also known as `style`, is a collection of declarations, targeting one or more selectors.
- A stylesheet is made up of multiple rules.
- In order to accommodate screens of different shapes and sizes, CSS features `media queries`
- `media queries` -> allow us to apply different CSS in different scenarios. 
- Media queries use the `@media` syntax. You can think of it as an `if` statement in JavaScript.
```
@media (condition) {
    /* Some CSS that'll run if the condition is met */
}
```
- `:hover` is an example of a `pseudo-class`.
- A `pseudo-class` is a selector modifier; it will apply its declarations when some sort of condition of state is met.
##### Combinator
- This selector is the combination of two different selectors: the `nav` tag, and the `a` tag.
- `descendent selector` -> space-seperated set of selectors, and matches `all` descendants, regardless of how deep the elements are nested.
- eg. `html a` will match all anchors on the page, since every `a` tag is technically a descendant of the top-level `<html>` tag.
#### Color
- HSL.
- The first number has the `deg` suffix since it's in degrees, and next two numbers are percentages.
- If you want your color to be semi-transparant, you can pass a fourth value for the `apha` channel. This is a unitless number between `0` (fully transparant) and 1 (the default, fully opaque).
#### Rem
- `rem` unit is quite a lot like the `em` unit, with one crucial difference - `it's always relative to the root element, the <html> tag`
- All of the rems across your app will be taking their cues from the root HTML tag. 
- By default, the HTML tag has a font size of `16px`, so `1rem` will be equal to `16px`
