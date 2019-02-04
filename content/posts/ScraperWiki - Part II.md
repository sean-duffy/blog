---
title: "ScraperWiki: Part II"
date: 2013-09-05T10:00:00Z
draft: false
---

I'm now in my fourth week at ScraperWiki, and have been working on all kinds of things. The project that I've had the most involvement in has been the development of the Wikipedia Infobox Tool. This is a currently incomplete tool for the ScraperWiki platform which extracts structured data from Wikipedia. It does this by parsing the contents of the [infoboxes](http://en.wikipedia.org/wiki/Wikipedia:Manual_of_Style/Infoboxes) on each article in a category and saving them into a database table, where each column is an infobox attribute and each row is an article.

Since most of the things I've been working on have involved getting data out of ambiguous formats, I've been using a lot of Regular Expressions. Before now I had only written short and simple regexes, so with the number of complex ones I've been writing recently, I think it's safe to say I'm now much better at writing them! To test my expressions before putting them to use, I've been using [RegExr](http://gskinner.com/RegExr/) by gSkinner, which has a lot of useful features to make writing and debugging complex regexes easier.

I've also learned a lot more about Git. Before coming to ScraperWiki I'd used Git, but only ever on my own small projects. Since these didn't involve collaboration and weren't very difficult to maintain, I had never used branches before and didn't have to think too much about how I did things. Working at ScraperWiki has definitely been a good opportunity to learn about branching, merging and rebasing and experience collaborating on a software project with Git.

Another thing to mention is that at ScraperWiki every employee and intern has to write an introductory blog post, and mine is scheduled to be posted soon! You can find the company blog [here](http://blog.scraperwiki.com), so be sure to look out for my post, and for the many other posts which may be of interest.
