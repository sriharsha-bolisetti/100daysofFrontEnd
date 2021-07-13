##### Flow Layout
- CSS implements several `layout modes`
- A layout mode includes a set of rules that govern how elements are laid out
- Flow layout is the default layout mode
- Inline elements don't want to make a fuss.
- You can shift things in the inline direction with margin-left and margin-right, but you can't change its width or height.
- There are two exceptions to inline fuss rule. The first is `replaced elements`
- A replaced element is one that embeds a foreign object. This includes `img, video, canvas`
- These elements are all technically inline, but they're special: they can affect block layout.
- Second exception is the `<button> tag`. They aren't quite replaced elements, but they function the same way. They can be given a width/height.
- Block Elements -> `fit-content` to shrink space
- Inline elements have `magic space` as browser treats them as if they're typography.
- Two ways to fix this 1. Set images to `display: block` 2. Set the `line-height` on the wrapping div to `0`
- `inline-block` -> Block in inline's clothing
##### Width Algorithms
- Block elements have a default width value of `auto`, not `100%`
- `width: auto` works very similar to `margin: auto`; it will grow as much as its able to, but no more.