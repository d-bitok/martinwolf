---
title: Force a concatenation order with gulp.js
author: Martin Wolf
layout: post
permalink: /2014/08/12/force-a-concatenation-order-with-gulp-js/
snap_isAutoPosted:
  - 1
snap_MYURL:
  - 
snapEdIT:
  - 1
snapFB:
  - 's:351:"a:1:{i:0;a:11:{s:4:"doFB";s:1:"1";s:10:"SNAPformat";s:35:"New post on MartinWolf.org: %TITLE%";s:9:"isAutoImg";s:1:"A";s:8:"imgToUse";s:0:"";s:9:"isAutoURL";s:1:"A";s:8:"urlToUse";s:0:"";s:8:"postType";s:1:"A";s:11:"isPrePosted";s:1:"1";s:8:"isPosted";s:1:"1";s:4:"pgID";s:31:"711305895599362_748412945221990";s:5:"pDate";s:19:"2014-08-12 09:36:47";}}";'
snapTW:
  - 's:280:"a:1:{i:0;a:9:{s:4:"doTW";s:1:"1";s:10:"SNAPformat";s:24:"[Article] %TITLE%: %URL%";s:8:"attchImg";s:1:"0";s:9:"isAutoImg";s:1:"A";s:8:"imgToUse";s:0:"";s:11:"isPrePosted";s:1:"1";s:8:"isPosted";s:1:"1";s:4:"pgID";s:18:"499127349452218370";s:5:"pDate";s:19:"2014-08-12 09:36:48";}}";'
categories:
  - Articles
tags:
  - concatenate
  - gulp.js
  - gulpfile
  - gulpjs
  - javascript
  - order
---
**A while back I made a [screencast][1] explaining my `gulpfile.js`. Since then my needs changed per project and recently I ran into a problem with my `js` task.  
**

The task should hint my manually edited `scripts.js` with JSHint, then concatenate that with jQuery and other third party scripts, run uglify and in the end save a `scripts.min.js` in a `/dist` folder. So far so good. Only problem was that the order in which the files got concatenated was totally random which is a problem because I needed jQuery at the top, then all the third party scripts and then my manually written code.

<!--more-->

Luckily there is a gulp plugin which can help us with that: [gulp-order][2]

You do everything like you did before but after you added all your sources you can reorder these and then keep doing whatever you want to do with the them. For me that looks like this:

<pre><code class="lang-javascript">gulp.task('js', function() {
    gulp.src('./js/scripts.js')
        .pipe(jshint())
        .pipe(jshint.reporter('default'))
        .pipe(addsrc('./js/_libs/*.js'))
        .pipe(order([
                'js/_libs/jquery-2.1.1.js',
                'js/_libs/jquery.bxslider.js',
                'js/_libs/jquery.form.js',
                'js/_libs/cf7.js',
                'js/scripts.js'
            ], { base: './' }))
        .pipe(concat('scripts.min.js'))
        .pipe(uglify({mangle: false}))
        .pipe(gulp.dest('./dist/js'));
});</code></pre>

I had to set the base option to &#8216;./&#8217;, which is the root of the project in order to make it work. This might not be necessary for you.

Happy coding!

 [1]: http://martinwolf.org/2014/06/17/screencast-explaining-my-gulpfile-js/
 [2]: https://github.com/sirlantis/gulp-order