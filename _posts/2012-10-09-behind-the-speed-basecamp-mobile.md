---
title: 'Behind the speed: Basecamp mobile'
author: Martin Wolf
layout: post
permalink: /2012/10/09/behind-the-speed-basecamp-mobile/
linked_list_url:
  - http://37signals.com/svn/posts/3269-behind-the-speed-basecamp-mobile
categories:
  - Linked List
tags:
  - 37signals
  - basecamp mobile
  - mobile
  - rwd
  - web app
---
<p class="linked-list-quote-author">
  Jason Z.:
</p>

> Making it fast required us to rebuild every view to include precisely what was relevant to the mobile experience and nothing else – not only in terms of design and features, but resources. There’s no extra mark-up, no unused styles, and we kept JavaScript usage to a minimum. That means no jQuery – in fact, no framework at all. We distilled the most common operations to a handful of helpers (about 70 lines of CoffeeScript) and the rest we wrote using the plain old DOM API. (What was most surprising to me is how much you can do without a framework when you don’t have to support Firefox and multiple versions of Internet Explorer!)

Great article about want went into making Basecamp mobile blazing fast.