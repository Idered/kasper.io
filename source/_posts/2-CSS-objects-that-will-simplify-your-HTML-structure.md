title: 2 CSS objects that will simplify your HTML structure
tags:
  - Uncategorized
date: 2014-11-11 00:00:00
---

I haven't posted anything for almost a year but during that time I've learned  a lot of useful stuff. Today I'll share with you two cool things that I use all the time. Split & Join objects will help you building your HTML structure. See demo at the [end of article](#demo).

## Basic settings and helper

```
$spacing-unit: 30px;
$breakpoint:   480px;

%clearfix:after {
    content: "";
    display: table;
    clear: both;
}
```

## Split

Classes:

* split &#8211; Base class used to split 2 elements
* split&#45;-table &#8211; Option used with .split class to split more elements
* split&#45;-responsive &#8211; Makes object responsive

```scss
.split {
    @extend %clearfix;

    > * {
        float: left;
    }

    > * + * {
        float: right;
    }

    &--table {
        display: table;
        width: 100%;
        table-layout:fixed;
        text-align: center;

        &:after {
            content: none;
        }

        > * {
            float: none;
            display: table-cell;
            vertical-align: middle;
        }

        > :first-child {
            text-align: left;
        }

        > :last-child {
            text-align: right;
        }
    }

    &--responsive {
        @media screen and (max-width: $breakpoint) {
            display: block;
            text-align: center;

            > * {
                float: none;
                display: inline-block;
            }

            > * + * {
                display: block;
                margin-top: $spacing-unit/2;
            }

            > :first-child,
            > :last-child {
                text-align: inherit;
            }
        }
    }
}
```

## Join

Classes:

*   join &#8211; Base class used to join multiple elements
*   join&#45;-tiny, join&#45;-small, join&#45;-large &#8211; Control spacing between elements
*   join&#45;-bottom, join&#45;-middle &#8211; Controll elements vertical alignment
*   join&#45;-force &#8211; Remove whitespace between elements using float
*   join&#45;-responsive &#8211; Makes object responsive

```scss
.join {
    > * {
        display: inline-block;
        vertical-align: top;
    }

    > * + * {
        margin-left: $spacing-unit;
    }

    &--middle > * { vertical-align: middle; }
    &--bottom > * { vertical-align: bottom; }

    &--tiny  > * + * { margin-left: $spacing-unit/4; }
    &--small > * + * { margin-left: $spacing-unit/2; }
    &--large > * + * { margin-left: $spacing-unit*2; }

    &--force {
        @extend %clearfix;

        > * {
            float: left;
        }
    }

    &--responsive {
        @media screen and (max-width: $breakpoint) {
            text-align: center;

            > * {
                float: none;
                display: inline-block;
            }

            > * + * {
                display: block;
                margin-left: 0;
                margin-top: $spacing-unit/2;
            }
        }
    }
}
```

<iframe width="100%" height="300" src="//jsfiddle.net/0fj0nmwp/1/embedded/result,html,css" allowfullscreen="allowfullscreen" frameborder="0"></iframe>
