# Fadeup-on-Scroll

This is basically a minimal version of the far more capable
[AOS Library](https://github.com/michalsnik/aos). The only functionality
included here is fading in HTML elements when they scroll into view from the
bottom of a page.

## Usage

To incorporate it into your project, simply copy fade-on-scroll.css and
fade-on-scroll.js into your project and add the appropriate `<script>` and
`<link>` tags to any html files you want to use the fade effect in.\
Note that the script must either be included at or near the end of `<body>`, or
be marked as `defer` (`<script src="wherever.js" defer></script>`).

Mark any elements you want to fade in on scroll using the `fade-on-scroll`
class:

```
<p class="fade-on-scroll">
	This will fade in when scrolling in from the bottom
</p>
```

## Customization

There are a few parameters that can be changed in order to influence the
appearance of the fade-in effect:
* css: .fade-on-scroll transition:\
  Changing the transition timings and types will impact the rate at which
  elements fade into view. For further information, see the relevant
  [MDN Documentation](https://developer.mozilla.org/en-US/docs/Web/CSS/transition).
* css: .fade-on-scroll transform:\
  This changes how far the element is offset to the bottom when it is
  off-screen. This will need to be increased when perc_threshold in
  fade-on-scroll.js is increased, so that elements do not start their fade-in
   from somewhere inside the screen.
* js: perc_threshold:\
  This sets the percentage of the window's height that must be below an
  element's upper edge for it to be considered 'on-screen'. Increasing this
  value will delay the fade-in, while decreasing it will make it start sooner.
  Note that only values from 0 (inclusive) to 1 (exclusive) are supported.

## Accessibility

The fade-in effect respects the
[prefers-reduced-motion](https://developer.mozilla.org/en-US/docs/Web/CSS/@media/prefers-reduced-motion)
css media query. If a user has set their preferences to reduced motion, no
fade-in will occur. Instead, all elements will be displayed normally.
