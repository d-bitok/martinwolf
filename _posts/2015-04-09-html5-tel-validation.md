---
title: HTML5 telephone input validation
layout: post
permalink: /2015/04/09/html5-telephone-input-validation/
format: article
---
**HTML5 offers a lot of awesome additions to the old school `input` element. For example a bunch of new input types like `number` or `email`.**

I recently created a simple callback form: The user should be able to insert a telephone number and hit the send button. Nothing more. Validation wasn't a big topic so I opted for a simple HTML5 validation check.

I added the input type `tel` to the input field as well as the `required` attribute.

{% highlight html %}
<input type="tel" placeholder="Telephone Number" required>
{% endhighlight %}

If a browser supports the new HTML5 form validation it won't send the form and show an error message as long as the field is empty. The input type will also make sure that a couple of touch devices like the iPhone will show a keyboard customized for telephone number input.

What type `tel` won't do is validate if the input is actually a telephone number. This is because there are a lot of different telephone number styles out there. You could use input type `number`. This has a validation process built in, but will show little arrows to count a number up and down and it will only allow numbers, no other characters like `+` or `(` and `)` which aren't unlikely in a telephone number.

Luckily you can define your own regex patterns against which to check the entered input. You do this with the `pattern` attribute.

{% highlight html %}
<input type="tel" pattern="^[0-9\-\+\s\()]*$" placeholder="Telephone Number" required>
{% endhighlight %}

If you are like me and don't have a lot of experience with regex patterns, this means all numbers (`0-9`), the minus symbol (`-`), the plus symbol (`+`) as well as spaces (`s`) and parentheses (`()`) are allowed.

If you enter anything else the form will not validate and you can't submit it. That's a very easy and lose telephone number validation but will be more than enough for a simple callback form. If someone comes along with an older browser ([check which browsers support the `pattern` attribute here](http://caniuse.com/#search=pattern)), enters something stupid and hits send, the world won't stop spinning. But the new attributes enhance the site for modern browsers, which is awesome.

If you need more specific patterns, [html5pattern.com](http://html5pattern.com/) offers a lot of them. Happy validating!
