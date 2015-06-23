# Mobile Safari Form Styling

Styling forms for mobile safari (and webkit) can be kind of weird, it adds a bunch of defaults to try and be helpful.

Next time you're panicking here, you can add:

    .thing {
      -webkit-border-radius: 0;
      -webkit-appearance: none;
    }

Mobile Safari will add border-radius no matter what, so that's sometimes necessary when doing iOS Browser stuff. `-webkit-appearance` takes care of weird shadows and things like that. Anyways, huzzah!