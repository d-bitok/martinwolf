---
title: Pure CSS radio and checkbox inputs
author: Martin Wolf
layout: post
permalink: /2013/09/13/pure-css-radio-and-checkbox-inputs/
snap_MYURL:
  - 
snapEdIT:
  - 1
snapFB:
  - 's:231:"a:1:{i:0;a:8:{s:4:"doFB";s:1:"1";s:8:"postType";s:1:"A";s:10:"AttachPost";s:1:"2";s:10:"SNAPformat";s:35:"New post on MartinWolf.org: %TITLE%";s:9:"isAutoImg";s:1:"A";s:8:"imgToUse";b:0;s:9:"isAutoURL";s:1:"A";s:8:"urlToUse";b:0;}}";'
snapTW:
  - 's:151:"a:1:{i:0;a:5:{s:4:"doTW";s:1:"1";s:10:"SNAPformat";s:24:"[Article] %TITLE%: %URL%";s:8:"attchImg";s:1:"0";s:9:"isAutoImg";s:1:"A";s:8:"imgToUse";b:0;}}";'
categories:
  - Articles
tags:
  - checkbox
  - css
  - form
  - input
  - radio
  - styling
---
In a recent project at work I needed to come up with a simple solution for styled radio and checkbox type inputs. While just styling the inputs works fine in Chrome and Safari if you apply `-webkit-appearance: none;`, it doesn&#8217;t work so well in Firefox even if you use `-moz-appearance: none;`.

So my solution uses pseudo elements which you can style as you want and labels which transfer the click to hidden input fields.

HTML markup:

<pre><code class="lang-markup">&lt;form&gt;
    &lt;input id="radio-input-1" type="radio" value="myValue 1" name="radio-group" checked&gt;
    &lt;label for="radio-input-1" class="input-helper input-helper--radio"&gt;myValue 1&lt;/label&gt;
    
    &lt;input id="radio-input-2" type="radio" value="myValue 2" name="radio-group"&gt;
    &lt;label for="radio-input-2" class="input-helper input-helper--radio"&gt;myValue 2&lt;/label&gt;
    
    &lt;input id="checkbox-input-1" type="checkbox" value="myValue 1" checked&gt;
    &lt;label for="checkbox-input-1" class="input-helper input-helper--checkbox"&gt;myValue 1&lt;/label&gt;
    
    &lt;input id="checkbox-input-2" type="checkbox" value="myValue 2"&gt;
    &lt;label for="checkbox-input-2" class="input-helper input-helper--checkbox"&gt;myValue 2&lt;/label&gt;
&lt;/form&gt;</code></pre>

Sass markup:

<pre><code class="lang-scss">.input-helper {
    position: relative;
    display: inline-block;
    
    &:before {
        content: '';
        display: block;
        position: absolute;
    }
}
 
.input-helper--radio {
    padding-left: 18px;
 
    &:before {
        top: 1px;
        left: 0;
        width: 10px;
        height: 10px;
        border-radius: 50%;
        border: 1px solid #222;
    }
}
 
.input-helper--checkbox {
    padding-left: 20px;
 
    &:before {
        top: 0;
        left: 0;
        width: 13px;
        height: 13px;
        border: 1px solid #222;
    }
}
 
input[type="radio"] {
    display: none;
 
    &:checked + label:before {
        background: #222;
    }
}
 
input[type="checkbox"] {
    display: none;
 
    &:checked + label:before {
        background: #222;
    }
}</code></pre>

I put together a CodePen so you can fiddle with it as much as you want:  
<http://codepen.io/martinwolf/pen/vLpwG>