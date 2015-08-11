title: Send forms using Ctrl + Enter
tags:
  - Uncategorized
date: 2013-02-25 00:00:00
---

Many times, after I finish writting my comment or post, I press `Ctrl + Enter` and &#8230; nothing. That's too bad, form should be sent after I press that shortcut but nothing happens. Here's a snippet which will help you add this function for your forms:

```
var isCtrl = false;

$('textarea, input').keyup(function(e) {
    if (e.which == 17) isCtrl = false;
}).keydown(function(e) {
    if (e.which == 17) isCtrl = true;
    if (e.which == 13 && isCtrl === true) {
        $(this).closest('form').submit();
        return false;
    }
});
```
    