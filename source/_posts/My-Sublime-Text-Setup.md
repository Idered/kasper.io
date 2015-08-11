title: My Sublime Text Setup
tags:
  - Uncategorized
date: 2014-01-11 00:00:00
---

I use Sublime Text 3 which is really fast and stable but without proper configuration and plugins you can't fully utilize it's power. My configuration is for Windows users, it aims for better HTML, CSS, JS, PHP, Markdown file edition and Git workflow.

## Visual look and configuration

Here's my top list of themes and color schemes:

1.  [Spacegray](http://kkga.github.io/spacegray/) &#8211; Ocean
2.  [Flatland](https://github.com/thinkpixellab/flatland) &#8211; Flatland Dark
3.  [Soda](http://buymeasoda.github.io/soda-theme/) &#8211; Soda Dark

I'm in love with Spacegray theme, together with Ocean color scheme, it's the best combination for night workers.

My font of choice is [Source Code Pro](http://sourceforge.net/projects/sourcecodepro.adobe/).

After installation, go to `Preferences -> Settings - User` and paste this config:

```
    {
        "bold_folder_labels": true,
        "caret_style": "phase",
        "color_scheme": "Packages/User/base16-ocean.dark (SL).tmTheme",
        "default_line_ending": "unix",
        "ensure_newline_at_eof_on_save": true,
        "fallback_encoding": "UTF-8",
        "font_face": "Source Code Pro",
        "font_size": 9,
        "highlight_line": true,
        "ignored_packages":
        [
            "Vintage",
            "Markdown"
        ],
        "line_padding_bottom": 2,
        "line_padding_top": 2,
        "overlay_scroll_bars": "enabled",
        "rulers":
        [
            80,
            120
        ],
        "shift_tab_unindent": true,
        "show_panel_on_build": false,
        "show_tab_close_buttons": false,
        "theme": "Spacegray.sublime-theme",
        "translate_tabs_to_spaces": true,
        "trim_trailing_white_space_on_save": true
    }
```

Names are quite straightforward so edit them to match your needs. For description of each option, check default settings.

Here're my shortcuts(`Preferences -> Key Bindings - User`) configuration:

```
[
    { "keys": ["ctrl+t"], "command": "toggle_side_bar" },
    { "keys": ["ctrl+v"], "command": "paste_and_indent" },
    { "keys": ["ctrl+shift+v"], "command": "paste" }
]
```

## Markdown

For Markdown, I use [MarkdownEditing](http://brettterpstra.com/projects/markdownediting). It has a nice dark theme, useful shortcuts and functions. Check it's github page for more information.

After installation, go to `Preferences -> Package Settings -> MarkdownEditing -> Markdown GFM Settings - User` and paste this settings:

```
{
    "color_scheme": "Packages/MarkdownEditing/MarkdownEditor-Dark.tmTheme"
}
```

Then open any `*.md` file, press `Ctrl + Shift + P`, write `markdown` and select `Set Syntax: Markdown GFM`.

Markdown edition is even better in distraction free mode, press `Shift + F11` to jump in.

## HTML, CSS and JavaScript

There're many useful plugins for those languages but what I really needed was fast code creation and validation.

### Code creation

For code creation, I use this plugins:

*   Emmet &#8211; abbreviation expander
*   Emmet Css Snippets &#8211; css abbreviation expander
*   HTML5 &#8211; snippets
*   HTML Attributes &#8211; attributes snippets
*   AutoFileName &#8211; helps typing path to files(try on img src)
*   DocBlockr &#8211; comment blocks

You can install all of those via Package Control, play with each one and read docs, it will help you to fully utilize them.

### Code validation

For code validation, I use [SublimeLinter](http://sublimelinter.readthedocs.org/en/latest/) and specific linters:

*   html-tidy
*   csslint
*   jslint
*   json
*   phpcs

There're also linters for other languages, to get full list, open Package Control and type `SublimeLinter`. Some of those require to install additional packages, check this [article](http://sublimelinter.readthedocs.org/en/latest/installation.html#linter-plugins) for more info.

### Other useful plugins

[Emmet LiveStyle](http://livestyle.emmet.io) is a plugin for live bi-directional CSS editing. It's a paid product but it's free during beta test.

BracketHighlighter extends editor bracket/tags highlighment and helps you to get better orientation in code.

[PlainTasks](https://github.com/aziz/PlainTasks) is great plugin for managing tasks/todos in editor. I use it for my personal projects.

## Git workflow

Yes, git is awesome but it's even more awesome to use it in your editor. There's a plugin for that, just use Package Control and type &#8220;Git&#8221;.

There's one more very useful plugin named `VCS Gutter`, it shows uncommited changes in editor gutter.

* * *

If you followed all this guide, installed all plugins and configured them properly then you should notice improvement in your workflow and code quality.

Here're 2 screens on how it looks for me:

[![Sublime Text :: PHP File](http://i.imgur.com/GFiO5iB.png)](http://i.imgur.com/GFiO5iB.png)

[![Sublime Text :: Markdown File](http://i.imgur.com/ZGpAIFV.png)](http://i.imgur.com/ZGpAIFV.png)