---
title: My Sass Breakpoints Mixin
layout: post
permalink: /2015/02/19/sass-breakpoints-mixin/
---
**Working on a website nowadays almost always means that you need to use media queries to make the website adapt to certain viewport sizes or environmental changes. It's rarely the case that you can omit them completely. I had such cases, but that only happens if the design is very very simple.**

In blank CSS using a media query looks like the following:

{% highlight css %}
.wrap {
    padding: 0 10px;
}

@media (min-width: 600px) {
    .wrap {
        padding: 0 30px;
    }

}
{% endhighlight %}

There are two problems with that. First, we have to repeat the class name and second it would be nice to have 600px as a variable so we don't have to remember it but could just call out "breakpoint 1" and change it in one place and thus change the whole project.

Sass can help us out in both cases. First, it allows us to nest the media query inside the `.wrap` block, second we can define a variable and use it project wide.

This would look like the that:

{% highlight scss %}
$bp1: 600px;

.wrap {
    padding: 0 10px;

    @media (min-width: $bp1) {
        padding: 0 30px;
    }
}
{% endhighlight %}

The resulting CSS is the same as our initial example.

## The complete Mixin

While that is already pretty good we can take it a step further and create a mixin which handles everything for us.

{% highlight scss %}
/**
 * Media Query Variables
 */
$mq-1: (min-width: 600px);
$mq-2: (min-width: 900px);
$mq-2-reverse: (max-width: 900px);
$mq-3: (min-width: 1200px);
$mq-retina: (-webkit-min-device-pixel-ratio: 2), (min-resolution: 192dpi), (-o-min-device-pixel-ratio: 2/1);

/**
 * Breakpoint Mixin
 */
@mixin breakpoint($point) {
    @if $point == bp1 {
        @media $mq-1 {
            @content;
        }
    }
    @if $point == bp2 {
        @media $mq-2 {
            @content;
        }
    }
    @if $point == bp2-reverse {
        @media $mq-2-reverse {
            @content;
        }
    }
    @if $point == bp3 {
        @media $mq-3 {
            @content;
        }
    }
    @elseif $point == retina {
        @media $mq-retina {
            @content;
        }
    }
}
{% endhighlight %}

{% highlight scss %}
.wrap {
    padding: 0 10px;

    @include breakpoint(bp1) {
        padding: 0 30px;
    }

    @include breakpoint(bp2) {
        padding: 0 50px;
    }
}
{% endhighlight %}

Inside the `.wrap` class we can call the breakpoint mixin and throw in the breakpoint name we want to use. The mixin then looks through the if statements and if the breakpoint name exists uses that and creates the media qeury with your styles.

The compiled CSS will look like that:

{% highlight css %}
.wrap {
    padding: 0 10px;
}

@media (min-width: 600px) {
    .wrap {
        padding: 0 30px;
    }
}

@media (min-width: 900px) {
    .wrap {
        padding: 0 50px;
    }
}
{% endhighlight %}

This allows us to define the breakpoints in only one place and use them across the whole project. It's the single point of truth which we could change in this one place and thus update the whole site. Because we can nest the mixins inside the class everything stays in one place and we can see how a class evolves across all breakpoints. This makes this technique really easy and fast to use and helps us to always stay in control of our styles.

My breakpoint values change on a per project basis. I try to avoid predefining breakpoints based on popular device sizes and rather set a breakpoint when one is actually needed. I get theses values while I develop and resize the browser. If the design looks bad or something isn't readable any more I know I need a new breakpoint.

Other times I predefine the breakpoints together with the designer before starting to code. But we always stay flexible and change the breakpoint values if necessary. That's important - don't tie yourself to some arbitrary widths someone defined if they make no sense for the project you are working on.

I have to say though, that I try to find a few universal breakpoint per project so that I don't have to deal with a dozen different breakpoints. I always try to keep things as simple as possible. If I need a media query for only one particular element for a very uncommon width, I write a media query manually. If I realize later on that I need the same media query in another place, I will go back and refactor the code so that it'll be part of the Breakpoint Mixin.

I hope this Mixins helps you to simplify your responsive development process or it at least inspires you to write your own mixin or come up with an even smarter solution.
