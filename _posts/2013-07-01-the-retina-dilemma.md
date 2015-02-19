---
title: The Retina Dilemma
author: Martin Wolf
layout: post
permalink: /2013/07/01/the-retina-dilemma/
categories:
  - Articles
tags:
  - connection
  - images
  - mobile
  - responsive
  - retina
---
**In recent days, weeks and months [a][1] [lot][2] [was][3] [written][4] [about][5] [responsive][6] and therefore retina images. We as a developer community have a few ideas how to solve the problems we face but as far as I can tell no proposal is really perfect – neither the picture element nor srcset. But it&#8217;s not only a problem of how to implement responsive images, it&#8217;s also a big philosophical question we have to answer.**

So even if we would have a perfect solution how to implement responsive and retina images we still have the problem, that small retina devices need really really big images but also have the slowest internet connection.  
This is a dilemma I recently stumbled upon again. We are working on a big responsive site which features two columns on bigger screens and only one column on smaller screens. This is nothing special and the right way to go I think, but we now face the problem that to some extent images on smaller screens are bigger than on larger screens. For example: a slider features three images besides each other on bigger screens and only one image on a smaller screen. These smaller screens have almost always a higher density than their desktop counterparts, which makes the images even bigger. So we build our site mobile first and only load images and scripts if necessary and try to keep the site fast and on the other hand we want it to look awesome and have to serve retina images. This is just a mess and as far as I can see there is no right answer or solution to our problem because it&#8217;s not a code problem.  
I hope the rumoured @4x screens will remain rumours.

What do you think about this dilemma and which way do you go? Load good looking retina images on mobile devices or keep the images small to make the site faster? And if the latter how do you explain this to your client who really really wants his products to look as good as possible?

 [1]: http://www.brucelawson.co.uk/2013/responsive-images-intrerim-report/
 [2]: http://daverupert.com/2013/06/ughck-images/
 [3]: http://timkadlec.com/2013/06/why-we-need-responsive-images/?utm_campaign=BDW-23-2013&utm_medium=email&utm_source=newsletter&utm_content=Why%20We%20Need%20Responsive%20Images
 [4]: http://dbushell.com/2013/06/03/the-raster-image-paradox/
 [5]: https://speakerdeck.com/davatron5000/mo-pixels-mo-problems
 [6]: http://responsivenews.co.uk/post/50092458307/images