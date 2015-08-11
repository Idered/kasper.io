title: Add anchors to your section titles
tags:
  - Uncategorized
date: 2013-02-02 00:00:00
---

It's really good UX practise to add anchors for your section titles. It helps users to link to a part of article. You can see a good example of this in README files on Github. Here's a [sample](https://github.com/Idered/zen-form).

Usualy we link `<a>` tag to an element using `id` attribute but this isn't supported by ASP websites. Instead of using `id`, we can use `name` attribute:

```
<a name="about" href="#about">About</a>
```

It's a link which points to itself. It's a section title so you also should wrap it in an `h2` or `h3` tag.

Optionaly we can add some style for anchor links:

```
[href^="#"] {
    position: relative;
    color: inherit;
}

[href^="#"]:hover {
    color: #e14a42;
}

[href^="#"]:hover:before {
    content: '#';
    right: 100%;
    position: absolute;
    margin-right: .2em;
}
```

Check out [demo page](/demo/add-anchors-to-your-section-titles).