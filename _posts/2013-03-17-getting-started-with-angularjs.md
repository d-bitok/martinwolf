---
title: Getting Started With AngularJS
author: Martin Wolf
layout: post
permalink: /2013/03/17/getting-started-with-angularjs/
categories:
  - Articles
tags:
  - angularjs
  - data binding
  - javascript
  - learning
  - tutorial
---
**Hello! I&#8217;m by no means a Javascript expert. In the past I mostly wrote HTML & CSS and sprinkled in JS in form of jQuery if I needed to. This worked fine.**

But now it&#8217;s time to expand my horizon and learn something new. This new thing is [AngularJS][1]. AngularJS is a Javscript framework from Google that allows us devs to build HTML5 web applications very easily. If you want to see what is possible with AngularJS, have a look at these [Case Studies][2].

I&#8217;ve already spend several hours reading tutorials and watching videos about using Angular but am still very much at the beginning. Until learning this new framework all I did wasn&#8217;t really programming so it&#8217;s sometimes a little bit difficult to understand what is going on. But I think Angular is beginner friendly and it helps that it&#8217;s well documented.

So while I was trying some stuff I thought why not let you guys in on my journey? So here we go. Our first steps in AngularJS. Explained in simple words.

The first thing I want to show you is the concept of Data Binding which is very important in AngularJS.

But before we can do anything we need to load Angular and tell our document that we want to build an app and so we add `ng-app` to our `html` tag which turns the whole document into an Angular App. You could also just add it to any element and only this element would be your app and thus have access to Angulars abilities.

<pre><code class="language-javascript">&lt;!DOCTYPE&gt;
&lt;html ng-app&gt;
    &lt;head&gt;    
        &lt;script src="http://cdnjs.cloudflare.com/ajax/libs/angular.js/1.0.1/angular.min.js"&gt;
    &lt;/head&gt;</code></pre>

In our example we&#8217;ll have two input fields of `type="number"` which will control the dimensions of a div and update it instantly.

<pre><code class="language-markup">&lt;label&gt;
    Width:
    &lt;input ng-model="width" type="number" placeholder="How about 300?"&gt;
&lt;/label&gt;
&lt;label&gt;
    Height:
    &lt;input ng-model="height" type="number" placeholder="For example: 200"&gt;
&lt;/label&gt;
    
&lt;div class="box" style="width: {{width}}px; height: {{height}}px; line-height: {{height}}px;"&gt;
    {{width}} x {{height}}
&lt;/div&gt;</code></pre>

So each of our input fields has the `ng-model` attribute with a specific name. Angular now binds the input of these fields to a variable with the same name. So if you type anything in one of the input fields it automatically gets output in your document. You do that by putting the name of the `ng-model` in curly braces, like so: `{{height}}`.

<!--more-->

In our example we use the values of our input fields to apply them to an inline style tag which controls the dimensions of a simple `div` element. I also output the values as text in the `div` just so you can see the values updating itself live. Setting the `line-height` to the height of the `div` makes sure the text is vertically centered.

Our example is already working without writing any Javascript at all. But I think it&#8217;s nice to add default values. We do that with a simple controller function. To access our code we need to add the `ng-controller` attribute to the element that contains our ng-models. That&#8217;s how we do it:

<pre><code class="language-markup">&lt;div ng-controller="ctrlSizing"&gt;
    ... Here are your inputs, etc ...
&lt;/div&gt;</code></pre>

In our Javascript file we write the controller function:

<pre><code class="language-javascript">function ctrlSizing($scope) {
    $scope.width = 200;
    $scope.height = 200;
}</code></pre>

That&#8217;s it. Through `$scope` you can see that we can only access the models which are in the scope of the current controller. If we would have added another `ng-model` which isn&#8217;t the controller `div` we couldn&#8217;t set it&#8217;s value.

If you want to see the example in action, have a look at this [Pen][3]:

<pre class="codepen" data-height="500" data-type="result" data-href="LmpeH" data-user="martinwolf" data-safe="true"><code></code><a href="http://codepen.io/martinwolf/pen/LmpeH">Check out this Pen!</a></pre>

 [1]: http://angularjs.org
 [2]: http://builtwith.angularjs.org/
 [3]: http://codepen.io/martinwolf/pen/LmpeH