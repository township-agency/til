# Ensuring Whitespace in Rendered Text
If you are rendering text with "built in" whitespace or new lines, ex: there are no `<br>` tags in the rendered text, you can actually ensure these new lines with CSS.

## Example from Cleverstack
Markup as it looks inside Chrome:
```html
<p class="reply-text">

new

line

again

</p>
```
This markup will not render with a new lines on those breaks, but adding `white-space: pre-wrap` to this element will ensure that the new lines are added.

Use `white-space: pre-wrap` when you want `<br>` functionality without the `<br>` tag.
