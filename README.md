# Dawn.css

An opinionated CSS Reset, based on Reboot.css by Bootstrap, which was built on Normalize.css.

So what's the difference?

## box-sizing best practice

I'm aware of the `details` bug in Google Chrome: [issue](https://github.com/twbs/bootstrap/issues/22872).

But still feel like we should use Chris Coyier's best practice and let Google fix the bug. Furthermore, how often do you use `details`?

More about the bug: [issue](https://bugs.chromium.org/p/chromium/issues/detail?id=589475)

So the settings for box-sizing in Dawn.css:

```
*,
*::before,
*::after {
  box-sizing: inherit;
}

html {
  box-sizing: border-box;
  ...
}
```

## 1rem = 10px

```
html {
  font-size: 62.5%;
  ...
}

body {
  font-size: 1.6rem;
  ...
}
```

The **font-size** in **html** is set to be **62.5%**, which equals 10px, and in **body** the **font-size** is set to **1.6rem**, so the font size for the whole website is still 16px, but the base **rem** equals **10px**, which is easier to calculate. If you want to h1 to be 24px, just set it to be 2.4rem, instead of 1.5rem.

All the other size settings were adjusted to the change.

## Added "Microsoft YaHei" to the font-family of the system font stack

```
body {
  font-family: -apple-system, BlinkMacSystemFont, "Microsoft YaHei", "Segoe UI", Roboto, "Helvetica Neue", Arial, "Noto Sans", sans-serif, "Apple Color Emoji", "Segoe UI Emoji", "Segoe UI Symbol", "Noto Color Emoji";
  ...
```

So that Chinese will be shown with the default "Microsoft Yahei" on Windows.

## License
MIT