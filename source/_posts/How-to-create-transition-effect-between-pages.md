title: How to create transition effect between pages
date: 2015-09-01 22:42:34
tags:
  - ui
  - javascript
  - effect
---

Yesterday I had a pleasure to work on minimalistic website. The design was nice so I got a little creative and created a nice transition effect between pages. It's a simple effect that doesn't require too much changes in your current project structure and should work nicely on most minimalistic websites.
 
![Fade in/out transition between pages](preview.gif)

You can view live example [here](http://pixelrevel.com).

First lets create CSS for our transitions:

```
.animate-in {
    -webkit-animation: fadeIn .5s ease-in;
    animation: fadeIn .5s ease-in;
}

.animate-out {
    -webkit-transition: opacity .5s;
    transition: opacity .5s;
    opacity: 0;
}

@-webkit-keyframes fadeIn {
    from { opacity: 0; }
    to { opacity: 1; }
}

@keyframes fadeIn {
    from { opacity: 0; }
    to { opacity: 1; }
}
```

Next step is to add `animate-in` on each page to `<body>` tag and after that, half of work is done - page has a nice fade in effect. 

Now we only have to add fade out effect just before page unloads. To do that we need a little of JavaScript:
 
```
window.addEventListener("beforeunload", function () {
  document.body.classList.add("animate-out");
});
```
