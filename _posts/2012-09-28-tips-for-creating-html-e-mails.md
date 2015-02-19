---
title: Tips for creating HTML e-mails
author: Martin Wolf
layout: post
permalink: /2012/09/28/tips-for-creating-html-e-mails/
categories:
  - Articles
tags:
  - advice
  - html
  - html e-mails
  - mailchimp
  - QUOTE.fm
  - tips
  - tricks
---
**HTML e-mails are great. Nobody really wants to look at boring plain text mails, but crafting them is really a pain in the ass. If you&#8217;ve never done it, I hope you never have to do it. But if the time comes, you might need some basic tips for creating HTML e-mails.**

The last few days I worked on new mails for [QUOTE.fm][1] and there are a few things I wrote down which might help some of you.

  * Put anything important inside the body tag because in-browser mail-clients like GMail almost always strip html and body tags
  * This also means forget classes and id&#8217;s, just write inline styles in every tag, sounds ridiculous, but works best
  * Use tables for as much as possible, it&#8217;s the only relatively safe way because of terrible html engines in (old) e-mail clients
  * Use table inside table inside table and so on
  * If you can, use the html background=&#8221;img.jpg&#8221; instead of the CSS equivalent
  * Same goes for all the other old things like `bgcolor="#000000"`, `align="center"`, `valign="bottom"`, `width="200"`, `height="60"`, and so on.
  * Use table rows and columns for padding
  * Check in a lot of e-mail clients with [MailChimp Inbox Inspection][2]
  * Learn to accept that, like websites don&#8217;t look exactly the same in every browser, e-mails don&#8217;t, too.
  * If you put a link on an img, make sure to also style the text appearance of the `a` tag, so that if images aren&#8217;t displayed, which is often the case in e-mail clients, your alt-text looks good

If you&#8217;re having problems building these old school table layouts don&#8217;t get frustrated, it means you&#8217;re a modern web developer, and that&#8217;s a good thing.

And so that you can get a feel for what it&#8217;s like to craft HTML e-mails I&#8217;ll show you the html of a rather simple one. It&#8217;s the upcoming new comment mail for QUOTE.fm. I also put the code up on [CodePen][3] so you can better inspect it, play around with it and see the result.

<pre style="white-space:pre;" class="language-markup"><code class="language-markup">&lt;!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd"&gt;
&lt;html&gt;

&lt;head&gt;
&lt;meta http-equiv="Content-type" content="text/html; charset=utf-8" /&gt;
&lt;meta name="author" content="Martin Wolf" /&gt;
&lt;title&gt;New Comment E-Mail&lt;/title&gt;
&lt;/head&gt;

&lt;body style="margin:0; padding:0;"&gt;
&lt;table cellpadding="0" cellspacing="0" border="0" width="100%" style="background-color:#fafafa"&gt;
    &lt;tbody&gt;
        &lt;tr&gt;
            &lt;td width="10"&gt;&lt;/td&gt;
            &lt;td height="25"&gt;&lt;/td&gt;
            &lt;td width="10"&gt;&lt;/td&gt;
        &lt;/tr&gt;
        &lt;tr&gt;
            &lt;td width="10"&gt;&lt;/td&gt;
            &lt;td&gt;
                &lt;table cellpadding="0" cellspacing="0" align="center" border="0" width="600" style="background: #ffffff; border: 1px solid #e1e1e1; border-radius: 4px;"&gt;
                    &lt;tbody&gt;
                        &lt;tr&gt;
                            &lt;td style="background-color:#0073a3; padding:17px 0px 14px 18px; border-top-left-radius: 4px;
border-top-right-radius: 4px;"&gt;&lt;a style="color:#ffffff; text-decoration: none; border:0;" href="http://quote.fm" target="_blank">&lt;img style="border:0;" src="http://files.quote.fm.s3.amazonaws.com/emails/quotefm-logo.png" width="100" height="23" alt="QUOTE.fm" /&gt;&lt;/a>&lt;/td&gt;
                        &lt;/tr&gt;
                        &lt;tr&gt;
                            &lt;td&gt;
                                &lt;table cellpadding="0" cellspacing="0" border="0" width="94%" align="center"&gt;
                                    &lt;tbody&gt;
                                        &lt;tr&gt;
                                            &lt;td colspan="2" height="30"&gt;&lt;/td&gt;
                                        &lt;/tr&gt;
                                        &lt;tr&gt;
                                            &lt;td width="50"&gt;&lt;img src="https://s3-eu-west-1.amazonaws.com/avatars.quote.fm/6b0f15dd1f8e119fc1da9c9083f458ff_40.png" width="40" height="40" alt="Marcel Wichmann" /&gt;&lt;/td&gt;
                                            &lt;td width="550"&gt;
                                                &lt;p style="margin:0; padding:0; color:#3c3c3c; font-family:Arial, Verdana, sans-serif; font-size:14px; line-height:23px;"&gt;&lt;a style="color:#0073a3; text-decoration:none; font-weight:bold;" href="http://quote.fm/uarrr" target="_blank">Marcel Wichmann&lt;/a> commented on &lt;a style="color:#0073a3; text-decoration:none;" href="http://quote.fm/martinwolf" target="_blank">Martin Wolf&lt;/a>'s recommendation:&lt;/p&gt;
                                            &lt;/td&gt;
                                        &lt;/tr&gt;
                                        &lt;tr&gt;
                                            &lt;td colspan="2" height="15"&gt;&lt;/td&gt;
                                        &lt;/tr&gt;
                                        &lt;tr&gt;
                                            &lt;td colspan="2" style="background:#f3f9fc; border:1px solid #d7dee1; border-radius:2px; padding:25px 20px;"&gt;
                                                &lt;p style="margin:0; padding:0; color:#3c3c3c; font-family:Arial, Verdana, sans-serif; font-size:14px; line-height:23px;"&gt;Youssef Sarhan ( &lt;a style="color:#0073a3; text-decoration:none;" href="#" target="_blank">youssefsarhan&lt;/a> ) on Google Glass and how it should be advertised. It's something that can change the life of every normal person, Google don't need to advertise it with extreme sports or fashion events.&lt;/p&gt;
                                            &lt;/td&gt;
                                        &lt;/tr&gt;
                                        &lt;tr&gt;
                                            &lt;td colspan="2" height="30"&gt;&lt;/td&gt;
                                        &lt;/tr&gt;
                                    &lt;/tbody&gt;
                                &lt;/table&gt;
                            &lt;/td&gt;
                        &lt;/tr&gt;
                        &lt;tr&gt;
                            &lt;td&gt;&lt;/td&gt;
                        &lt;/tr&gt;
                    &lt;/tbody&gt;
                &lt;/table&gt;
            &lt;/td&gt;
            &lt;td width="10"&gt;&lt;/td&gt;
        &lt;/tr&gt;
        &lt;tr&gt;
            &lt;td width="10"&gt;&lt;/td&gt;
            &lt;td valign="middle"&gt;
                &lt;table cellpadding="0" cellspacing="0" align="center" border="0" width="600"&gt;
                    &lt;tr&gt;
                        &lt;td height="20"&gt;&lt;/td&gt;
                    &lt;/tr&gt;
                    &lt;tr&gt;
                        &lt;td align="center"&gt;
                            &lt;a style="display:block; padding:20px 0; width:100%; color:#3c3c3c; font-family:Verdana, Arial, sans-serif; font-size:12px; line-height:12px; text-decoration:none; text-align:center; border:1px solid #d5d5d5; border-radius:2px; background:#f5f5f5; box-shadow: inset 0 1px 0 #fff;" href="quote.fm/#" target="_blank">Respond on QUOTE.fm&lt;/a>
                        &lt;/td&gt;
                    &lt;/tr&gt;
                    &lt;tr&gt;
                        &lt;td height="10"&gt;&lt;/td&gt;
                    &lt;/tr&gt;
                    &lt;tr&gt;
                        &lt;td&gt;
                            &lt;p style="color:#6b6b6b; font-family:Verdana, Arial, sans-serif; font-size:11px; line-height:14px; text-align:center;"&gt;You selected to receive email notifications when you've got a new comment.&lt;br /&gt;To stop receiving these emails, you can turn off notifications &lt;a style="color:#0073a3; text-decoration:none;" href="#">here&lt;/a>.&lt;/p&gt;
                        &lt;/td&gt;
                    &lt;/tr&gt;
                    &lt;tr&gt;
                        &lt;td height="10"&gt;&lt;/td&gt;
                    &lt;/tr&gt;
                &lt;/table&gt;
            &lt;/td&gt;
            &lt;td width="10"&gt;&lt;/td&gt;
        &lt;/tr&gt;
    &lt;/tbody&gt;
&lt;/table&gt;

&lt;/body&gt;

&lt;/html&gt;</code></pre>

 [1]: http://quote.fm
 [2]: http://mailchimp.com/features/inbox-inspector/
 [3]: http://codepen.io/martinwolf/pen/mDybg