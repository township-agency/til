# Pseudo Element Unicode Characters

This is so stupid but I always mix up the `Unicode Number` with the `HTML Code` and how to escape the characters. 

Say you want to do something like to put an arrow `after` some text. Go look up the unicode character ([a rightwards arrow for example](http://unicode-table.com/en/2192/)) and get the `Unicode Number`. In this case, we have `2192`. To include that `before` or `after` your selector, you simply proceed the number with a forward slash. 

```html
<a href="/about" class="action">About</a>
```

```scss
.action {
  &::after {
    content: "\2192"
  }
}
```

Rendered in HTML, this will give you: About &#8594;

👏🏽
