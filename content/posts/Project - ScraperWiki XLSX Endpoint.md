---
title: "Project: ScraperWiki XLSX Endpoint"
date: 2014-09-08T10:00:00Z
draft: false
tags: ["project"]
---

This summer I was invited to work for [ScraperWiki]({{< ref "posts/ScraperWiki - Part I.md" >}}), and this post is about the project I spent most of my time on during this internship. The project in question was rewriting an endpoint that converts data in a SQL database to Excel Spreadsheet (XLSX) form for users to download and use. The current program was written in Python but was fairly slow and had the problem of consuming large amounts of system memory, sometimes causing failures in large datasets. 

Previously I was mostly doing Python development at ScraperWiki, but they've been moving a lot of their new development to [Go](http://golang.org), so after introducing me to the problem, Peter gave me a quick introduction to Go and helped get me started on what I'd be spending the next few weeks on. The proposal was to rewrite the program in such a way that it streamed the XLSX file to the user as it generated it, allowing it to run in a constantly sized window of memory. This also led to a speedup, as did it being written in Go, a compiled language.

I did this by building on [psmithuk's xlsx](https://github.com/psmithuk/xlsx), which is a Go package for writing XLSX Spreadsheets. This package provided a great starting point, as I rewrote it in a way that could support streaming generation as described above. There were also many other changes needed, such as supporting XLSX files with multiple sheets, that required some reverse engineering and experimentation with the XLSX format. There is a [standard](http://www.ecma-international.org/publications/standards/Ecma-376.htm) for the format, but it's very unwieldy and I found that running 'diff' between my generated files and identical correct files written by Excel was often an easier way to find out where I'd gone wrong. 

The fully functioning software currently lives in [ScraperWiki's fork of it](https://github.com/scraperwiki/xlsx/), but we're in the process of up-streaming it to psmithuk's repository. The other part of this XLSX endpoint is found [here](https://github.com/scraperwiki/xlsx-cgi).

The XLSX endpoint was my main project at ScraperWiki and I'm glad to say that it is fully deployed on the ScraperWiki website! It is a lot faster and deals much better with large sheets, with the peak memory usage being on the order of tens of megabytes rather than a potentially a few gigabytes as before.
