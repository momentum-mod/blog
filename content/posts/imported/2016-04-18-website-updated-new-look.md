---
markup: html
date: '2016-04-18T12:22:34+00:00'
draft: false
categories:
 - photo
tags: 
 - Website
 - GameDev
 - Momentum
 - NewLook
title: 'Website Updated - New Look!'
showDate: yes
url: /post/143004091779/website-updated-new-look
---

<p>Our website has finally been updated, and the frontend is now no longer just a placeholder! We’ve switched from the Javascript-based blog template to a lightweight and modern bootstrap frontend, complete with comprehensive mobile support. This update required us to completely re-write all the HTML and CSS for the frontend, as well as make many changes to the underlying Python/Flask backend.&nbsp;</p><p>However, the new website makes effective use of 

Jinja2

′s in-HTML python interpreter, which allows us to extend the layout easily and create new pages quickly, as well as control the content inside a single HTML document. The backend was also overhauled to make management easier, with essential text controlled by the database rather than baked inside the HTML, allowing admins to make changes easily and quickly.&nbsp;</p><p>The leaderboards also received a complete overhaul. Yet, much like the rest of Momentum, are far from finished. On the previous website, we had some issues with pagination of the times database, since the datatables.net JavaScript code assumes that the entire database will be returned with a single query, but we were only returning 20 entries at once due to the pagination. We did this pagination to prevent the entire database from being queried every time someone loaded the leaderboards page, but this made the leaderboards un-sortable beyond the 20 entries on a given page.&nbsp;</p><p>We changed this to use the 

JavaScript 

-based pages from the datatables.net script. Currently, the front page lists the most recent 150 runs completed, with individual pages filtered by map, by player, and per run. 

 As we update the web backend API to support the new statistics we are now collecting for times in-game, all of these statistics will become available for every run on the web.</p><p>You can check out the website at <a href="http://momentum-mod.org">http://momentum-mod.org</a></p><p>Finally, if you’re interested in being notified when we enter public alpha testing, you can sign up for our <a href="http://momentum-mod.org/mailinglist">mailing list</a>&nbsp;and we’ll email you when we release a public alpha build that you can try!</p><p>That's all for now!</p><p>Momentum Mod Development Team<br></p>