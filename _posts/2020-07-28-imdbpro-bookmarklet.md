---
layout: single
title: IMDbPro Bookmarklet
excerpt: Easy access for subscribers, regardless of how annoying the ads get
date: '2020-07-28T00:00:00-07:00'
categories:
- Blog
tags:
- Acting
- Bookmarklet
- Javascript
---
[Many years ago](http://web.archive.org/web/20120419154621/http://www.kevinashworth.com/blog/archives/category/technology/tech-tips), I offered a bookmarklet that makes life easier for users with IMDbPro subscriptions. Today, I am posting this updated version, free for your use.

Once installed properly, this bookmarklet does two things:
1. It takes you to a specific IMDbPro page if you click it when you’re _not_ already on IMDb. (The specific page is the one shown in the blue input box. Use mine, as shown, or enter the one you want for your own browser.)
2. If you’re already _on_ a regular IMDb page when you click this bookmarklet, you’ll be whisked to the IMDbPro version of it.

<input onblur="javascript:bookmarklet_change(this.value);" value="https://pro.imdb.com/name/nm2825198/">{: .notice--info}
So, first enter your “home” URL above, and then drag this link to your bookmarks bar, and you’re good to go: <a class="btn btn--info btn--small" id="imdbprobookmarklet" href="javascript:h=location.href;i=h.indexOf(%27imdb.com%27);p=h.indexOf(%27https://pro.imdb.com%27);t=h.indexOf(%27title%27);c=h.indexOf(%27combined%27);f=h.indexOf(%27fullcredits%27);r=h.indexOf(%27reference%27);badword=Math.max(c,f,r);if(i==-1) {window.location=%27https://pro.imdb.com/name/nm2825198/%27}else if(p==0) {window.location=h.replace(%27https://pro%27,%27https://www%27)}else if(p==-1){if((t>1)&&(badword>1)){h=h.substring(0,badword)}window.location=h.replace(/https:\/\/[a-z]+/,%27https://pro%27);};">IMDbPro</a>

_Wondering what the heck a bookmarklet is? [Click here](https://en.wikipedia.org/wiki/Bookmarklet)._

<script type="text/javascript" charset="utf-8">
function bookmarklet_change(url) {
  let bm = document.getElementById('imdbprobookmarklet');
  bm.href = bm.href.replace("https://pro.imdb.com/name/nm2825198/", url);
}
</script>
