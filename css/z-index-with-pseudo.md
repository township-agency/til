# Z-Index with Pseudo Elements
## Said Differently—Positioning Pseudo Elements with `position: absolute`

Sometimes I want to do a weird thing with an element, let's say, a weird "underline" that retracts on hover. Maybe it's more complicated than a simple underline, or border, so for that, I'll use a pseudo element to give me some flexibility.

If you want to _absolutely_ position a pseudo element _behind_ it's parent element, you have to do a couple things: 

1. Set the parent element to `position: relative` (you should usually do this when positioning outside of `static`)
2. Set the `z-index` of the pseudo element (if `before`) to `z-index: -1`

This will give you a pseudo element _behind_ the parent element without needing to set the `z-index` of the parent element. This can be useful if you want a creative button background, slightly modified underline, a background image, etc.

### Example

For [Cleverstack](https://cleverstack.com), we had this interesting type treatment where the border was raised ~`6px` from the baseline. 

To accomplish this, all you need is the following CSS

```scss

.footer-heading {
  position: relative;
  
  &::before {
    content: "";
    height: 2px;
    width: 100%;
    position: absolute;
    bottom: 4px;
    background-color: $color-black;
    z-index:-1;
  }
}

```
