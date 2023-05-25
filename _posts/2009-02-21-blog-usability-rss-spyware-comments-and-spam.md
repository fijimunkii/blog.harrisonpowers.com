---
layout: post
title: blog usability - rss, spyware, comments and spam
categories:
- usability
- wordpress
tags: []
---
According to a <a href="http://www.catalystgroupdesign.com/cofactors/?p=111" target="_blank">study</a> by Catalyst Group Design, <strong>mainstream consumers typically do not understand RSS, what it stands for or what it does</strong>.  They recognize the brightly colored xml or rss buttons, while not knowing the intended use.<br /><br />

<!--more-->In addition, when explained the concept users were fearful of having to installing anything, spyware, as well as being wary of having to pay for this service.<br /><br />

I found this observation interesting:
<blockquote>The fear of spam and spyware cannot be underestimated, as it seems that mainstream experience with the web is teaching users to be extremely wary of persistent or automated functions that are not enabled through trusted sources.</blockquote>
Spyware used to be a major issue, but with modern browsers becoming extremely secure there is not as much to worry about.
<br /><br />
I posted a screencast on <a href="http://blog.harrisonpowers.com/2009/02/08/rss-and-google-reader/" target="_self">how to use RSS and Google Reader</a>.  According to <a href="http://www.addthis.com/blog/2007/10/15/social-trends-for-september/" target="_blank">statistics</a> from addthis.com, it is easily the most popular reader.  There are <a href="http://scobleizer.com/2007/10/15/how-many-people-use-rss-anyway/" target="_blank">millions of people</a> subscribed to blogs through Google Reader.
<br /><br />
As RSS is a major component of the blogging system, it is beneficial for any blog to have instructions on how to use its syndication and how safe it is.  Likewise, as email updates are useful it is always good to inform the user that their email address is safe with you.
<br /><br />
Another way to make RSS on your blog more accessible is to subscribe to <a href="http://feedburner.com" target="_blank">FeedBurner</a>, a service that makes your rss feed viewable in a browser.  It also provides you with statistics.  Check out the <a href="http://wordpress.org/extend/plugins/feedburner-plugin/" target="_blank">Wordpress FeedBurner plugin</a>.  Tweet your blog updates automatically through RSS with <a href="http://twitterfeed.com" target="_blank">twitterfeed</a>.
<br /><br />
The Catalyst study points out that most users understand how to submit a comment, provided that the comment box is open at the bottom of the post.  But there was confusion as to the comment itself, its magnitude and how the blog published it.
<br /><br />
It is important to take into account the <strong>design and moderation of the commenting field</strong> when creating a blog.
<br /><br />
Usability can be interfered with by spam<strong>.</strong> Spam mucks up a website and nobody wants to sift through it to get to content. Personally, if I recognize spam I will stop reading a website.  Unfortunately, spammers have been targeting blogs
<br /><br />
A way to avoid their wrath is to initialize a CAPTCHA, or disable comments from unregistered visitors. The latter would hurt usability on a mainstream blog, so let's take a look at the CAPTCHA.
<br /><br />
What is a CAPTCHA?  Come on, you all know what it is.<br /><br />Of course you do. <strong>A CAPTCHA is a system for detecting if the user is human.</strong> The acronym stands for Completely Automated Public Turing Test to Tell Computers and Humans Apart.  Computers can actually get past CAPTCHAs like the one pictured above, so that's why you see the crazy ones with lines and colors that are sometimes illegible.
<br /><br />
Sure, usability takes a small hit with these, but the user is only prompted with the CAPTCHA after their post is written.  If it was a good post you can be sure the user will try and submit it.  Keep in mind the obvious problem with handicap accessibility.  Here is a report on <a href="http://cups.cs.cmu.edu/soups/2008/proceedings/p44Yan.pdf" target="_blank">usability issues in CAPTCHA design</a>.
<br /><br />
Another type of CAPTCHA that I like, which is handcap accessible, is math related.  <a href="http://sw-guide.de/wordpress/plugins/math-comment-spam-protection/" target="_blank">This wordpress plugin</a> will generate an encrypted math problem that the user has to solve.<br /><br />

Free (popular) wordpress plugin <a href="http://akismet.com/" target="_blank">Akismet</a> checks comments and filters those that look like spam.  The plugin is easy to install through your wordpress dashboard, and to activate it you need an <a href="http://faq.wordpress.com/2006/05/19/akismet-a-wordpresscom-blog-and-the-api-key/" target="_blank">API key</a> that is given to you for signing up on <a href="http://wordpress.com" target="_blank">wordpress.com</a>.
<br /><br />
Probably the most important comment related plugin you can install is <a href="http://txfx.net/code/wordpress/subscribe-to-comments/" target="_blank">Subscribe to Comments</a>.  This plugin provides the user with a checkbox by the comment field to subscribe to email notification of other comments to the post.
