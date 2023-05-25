---
layout: post
title: gmail labs - the freshbox
categories:
- google
tags: []
---
If you're like me, you live inside of Gmail and deal with a neverending stream of information.  Having your Gmail properly set up with labs can greatly improve the efficiency of dealing with, categorizing, and prioritizing the emails in your inbox.  I have figured out a system that works for me, and I would like to share it with you.

First of all, this guide requires that you have a few labs enabled.  To manage your Gmail labs, <a title="gmail labs settings" href="https://mail.google.com/mail/?shva=1#settings/labs" target="_blank">click here</a> and read along with my guide.

These are the labs that I have turned on, in the order they appear on the labs page.  I recommend you turn on all the labs I have list, those bolded will be detailed below. Please don't be alarmed at the size of this list.  Just about everything on it is quite useful.

<ol>
	<li>YouTube previews in mail</li>
	<li>Picasa previews in mail</li>
	<li>Flickr previews in mail</li>
	<li>Yelp previews in mail</li>
	<li>Google Voice player in mail</li>
	<li>Google Docs previews in mail</li>
	<li>Message translation</li>
	<li><strong>Quick Links</strong></li>
	<li><strong>Superstars</strong></li>
	<li>Pictures in chat</li>
	<li>Fixed width font</li>
	<li>Custom keyboard shortcuts</li>
	<li>Advanced IMAP Controls</li>
	<li>Default 'Reply to all'</li>
	<li>Quote selected text</li>
	<li>Navbar drag and drop</li>
	<li>Forgotten Attachment Detector</li>
	<li>Mark as Read Button</li>
	<li>Go to label</li>
	<li>Inbox preview</li>
	<li><strong>Multiple Inboxes</strong></li>
	<li>Google Search</li>
	<li>Create a Document</li>
	<li>Filter import/export</li>
	<li>Text Messaging (SMS) in Chat</li>
	<li>Authentication icon for verified senders</li>
	<li>Send &amp; Archive</li>
	<li>Undo Send</li>
	<li>Title Tweaks</li>
	<li>Don't forget Bob</li>
	<li>Got the wrong Bob?</li>
	<li>Green Robot!</li>
	<li>Hide read labels.</li>
	<li>Mark Unread From Here</li>
	<li>Google Calendar gadget</li>
	<li>Google Docs gadget</li>
	<li>Add any gadget by URL</li>
</ol>
My favorites are the Superstars and Multiple Inboxes, the interaction of which is beautiful.  The Superstars allow you to apply different types of stars to your emails and Multiple Inboxes give you quick access to information that is likely to be referenced, such as emails you have recently starred.  My favorite additional inbox is what I call the Freshbox, it simply displays my unread emails.  Also of great usage are the Quick Links, which provide easy access to saved searches.  I will explain how I've set up these labs, starting with the Superstars.<br /><br />

You can manage which stars are enabled and in which order on the <a title="superstar gmail settings" href="https://mail.google.com/mail/?shva=1#settings/general" target="_blank">General Gmail Settings page</a>.  Simply drag and drop them.  I use:<br />
<br />
<strong>Blue square</strong> for emails with INFORMATION that I may want to refer to in the future.
<br />
<strong>Red exclamation point</strong> or BANG for emails that I need to act on ASAP
<br />
<strong>Red star</strong> for emails with DATES like meetings, appointments, parties
<br />
<strong>Purple star</strong> for SPECIAL emails that I want to want to save for a rainy day
<br />
and <strong>Orange >></strong> for delegated emails, stuff I've sent out that needs to be returned to me
<br /><br />
These stars allow me to quickly prioritize what flows through my inbox.  Not a replacement for labels whatsoever, these stars work in conjunction.  For instance, I can click on my work label and see which emails are set with a red bang.  Similarly in the work label I can quickly spot emails with important documents by the info tag.
<br /><br />
Now, the grandaddy lab: Multiple Inboxes.  What this lab does is allow you to create additional inboxes.  These inboxes can be placed on top of, which I prefer, or to the right of or below the regular inbox.  These additional inboxes show the results of a search query that you specify in your <a title="multiple inboxes management" href="https://mail.google.com/mail/?shva=1#settings/lighttlist" target="_blank">Multiple Inboxes settings</a>.  These search queries could be anything you like.  I have mine set to show the Freshbox, Superstars and Chats.  The parameters I used to set up are as follows:

```
Pane 0: Query: is:unread in:inbox -in:buzz Title: Freshbox
Pane 1: Query: l:^ss_cr Title: ASAP
Panel 2: Query: l:^ss_sr Title: Dates
Panel 3: Query: l:^ss_cb Title: Reference
Panel 4: Query: label:chat Title: Chatbox
```

Have the maximum page size set to show <span style="color: #008080;">10</span> conversations per page for the new inbox panes and have them set <span style="color: #008080;">above</span> the inbox.
<br /><br />
One last important thing left to set up are the Quick Links.  Once you've enabled this lab a widget will appear on the left-side of your Gmail.  After performing any search in Gmail, clicking 'Add Quick Link' will save the current search in a handy link with a name of your choosing.  So, do a search for ```l:^ss_sp``` and create a quick link for your special, rainy-day emails.  Likewise make a search for ```l:^ss_co``` and create a quick link for the emails you're waiting on.  Here's a quick link to all the files you've emailed ```from:me;has:attachment```.  For a complete list of the search terms for superstars, see this lifehacker article on <a href="http://lifehacker.com/5321180/turn-gmail-into-your-ultimate-gtd-inbox" target="_blank">Gmail GTD</a> that initially inspired me.
