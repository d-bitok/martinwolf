---
title: BEM, Multiple Modifiers, and Experimenting with Attribute Selectors
author: Martin Wolf
layout: post
permalink: /2013/12/20/bem-multiple-modifiers-and-experimenting-with-attribute-selectors/
linked_list_url:
  - http://viget.com/extend/bem-multiple-modifiers-and-experimenting-with-attribute-selectors
nxs_snap_sh_FB0_1387529593:
  - 'a:24:{s:4:"doFB";i:1;s:5:"nName";s:8:"Facebook";s:7:"fbAppID";s:15:"547424155328706";s:8:"fbAppSec";s:32:"7cb4de34e0ff8039f7c03541f99c8105";s:8:"catSelEd";s:0:"";s:10:"fbPostType";s:1:"A";s:7:"fbAttch";s:1:"2";s:12:"fbAttchAsVid";i:0;s:6:"imgUpl";s:1:"1";s:11:"fbMsgFormat";s:38:"New post on TheAmazingWeb.net: %TITLE%";s:10:"fbMsgAFrmt";s:0:"";s:10:"riComments";i:0;s:12:"riCommentsAA";i:0;s:5:"fbURL";s:41:"https://www.facebook.com/visuellegedanken";s:6:"fbPgID";s:16:"visuellegedanken";s:6:"catSel";s:1:"0";s:14:"fbAppAuthToken";s:183:"CAAHx4R5R4MIBAN5RO4N873D8mKgRvoi8q7mqc9djALiq5tkKfAbmI84x09uohZAzhxGmW8e9vHWKp3ezhz9WnIywE5yi4kyZA4UyZAMFgJZAhTimmRtcgZC6jqvZCtj5BEFPbq76oKuIKxrxPJR9K1KR7bBupOnGFlzYXF61AXITbDcshKaXN2";s:18:"fbAppPageAuthToken";s:183:"CAAHx4R5R4MIBAN5RO4N873D8mKgRvoi8q7mqc9djALiq5tkKfAbmI84x09uohZAzhxGmW8e9vHWKp3ezhz9WnIywE5yi4kyZA4UyZAMFgJZAhTimmRtcgZC6jqvZCtj5BEFPbq76oKuIKxrxPJR9K1KR7bBupOnGFlzYXF61AXITbDcshKaXN2";s:13:"fbAppAuthUser";s:10:"1607117196";s:8:"isPosted";s:0:"";s:8:"imgToUse";b:0;s:8:"urlToUse";b:0;s:2:"ii";i:0;s:9:"timeToRun";i:1387529593;}'
snap_isAutoPosted:
  - 1
nxs_snap_sh_TW0_1387529590:
  - 'a:19:{s:4:"doTW";i:1;s:5:"nName";s:11:"_martinwolf";s:5:"twURL";s:30:"http://twitter.com/_martinwolf";s:9:"twConsKey";s:22:"43f4ucgXHmQ656M02ZBUxw";s:9:"twConsSec";s:42:"DrRkkZBFd0cClZD7dkNzUgimG9yud45yXIaXPUXn3c";s:10:"twAccToken";s:50:"15392033-DNYwP7PucUC9UGuba81ugP89CLdCf7MBB0zy3G9js";s:8:"catSelEd";s:0:"";s:10:"riComments";i:0;s:11:"riCommentsM";i:0;s:12:"riCommentsAA";i:0;s:13:"twAccTokenSec";s:42:"dnlfWj0ZBmBlrSpOVL7wJkFMfOc7Hfgexj7ykUKsXM";s:11:"twMsgFormat";s:35:"%TITLE%: %URL% (by @tommyjmarshall)";s:8:"attchImg";i:0;s:4:"twOK";i:1;s:6:"catSel";s:1:"0";s:8:"isPosted";s:0:"";s:8:"imgToUse";b:0;s:2:"ii";i:0;s:9:"timeToRun";i:1387529590;}'
snap_MYURL:
  - 
snapEdIT:
  - 1
snapTW:
  - 's:288:"a:1:{i:0;a:9:{s:4:"doTW";s:1:"1";s:10:"SNAPformat";s:35:"%TITLE%: %URL% (by @tommyjmarshall)";s:8:"attchImg";s:1:"0";s:9:"isAutoImg";s:1:"A";s:8:"imgToUse";b:0;s:11:"isPrePosted";s:1:"1";s:8:"isPosted";s:1:"1";s:4:"pgID";s:18:"413955224408449024";s:5:"pDate";s:19:"2013-12-20 08:53:11";}}";'
snapFB:
  - 's:371:"a:1:{i:0;a:12:{s:4:"doFB";s:1:"1";s:8:"PostType";s:1:"A";s:10:"AttachPost";s:1:"2";s:10:"SNAPformat";s:38:"New post on TheAmazingWeb.net: %TITLE%";s:9:"isAutoImg";s:1:"A";s:8:"imgToUse";b:0;s:9:"isAutoURL";s:1:"A";s:8:"urlToUse";b:0;s:11:"isPrePosted";s:1:"1";s:8:"isPosted";s:1:"1";s:4:"pgID";s:28:"1607117196_10201183678146510";s:5:"pDate";s:19:"2013-12-20 08:53:16";}}";'
categories:
  - Linked List
tags:
  - attribute selectors
  - bem
  - css
  - scss
---
<p class="linked-list-quote-author">
  Tommy Marshall:
</p>

> Thanks to the long supported CSS attribute selectors, we can extend the use of BEM even further to allow for multiple selectors.

That&#8217;s a really interesting experiment, but like Tommy said nothing I&#8217;d really wanted to use in a real project because of it&#8217;s drawbacks. I also don&#8217;t like it if my SCSS generates too much through Mixins. It&#8217;s hard to understand if you are new to a project or even if you haven&#8217;t had a look at it for a long time. /[via][1]

 [1]: https://twitter.com/wpSEO/status/413943095815045120