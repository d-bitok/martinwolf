---
title: Client Hints
author: Martin Wolf
layout: post
permalink: /2013/09/16/client-hints/
linked_list_url:
  - https://github.com/igrigorik/http-client-hints
categories:
  - Linked List
tags:
  - client hints
  - draft
---
<p class="linked-list-quote-author">
  Ilya Grigorik:
</p>

> This document defines a new request Client Hint header field, "CH", that allows the client to make available hints, both static and dynamic, to origin and intermediate servers about its preference and capabilities. "CH" allows server-side content adaption without imposing additional latency on the client, requiring the use of additional device databases, while allowing cache-friendly deployments.

Even though this draft exists since a few months today is the first time I had a closer look at it and I hope this gets implemented in browsers fairly soon. Client Hints would for example help solving the responsive images problem in a huge way.