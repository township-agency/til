If you want to select a class where all the class-names begin with `is-dash` for example—in my case indicating that I'm on the dashboard—you can do the following:

```css

[class^="is-dash"],
[class*=' is-dash'] {
  position: fixed;
}
```

I was in the position of some class-names being generated and indicating what state/route I was on. I wanted to change a particular navigation item when I was any dashboard state or substate (the names always started with `is-dash`).

With this, I can select all of them at the same time and ensure any future substates will be covered.
