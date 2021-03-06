---
title: "Project: Portfolio Tool"
date: 2013-07-15T10:00:00Z
draft: false
tags: ["project"]
---

This is a web application I built in late 2012 while I was studying [Computational Investing](https://www.coursera.org/course/compinvesting1), an online course offered by coursera.org which provides an introduction to the programming side of quantitative analysis for finance, dealing particularly with hedge funds. I really enjoyed this course and I'd recommend it to anyone interested in computer science, finance, or both. It assumes only a basic knowledge of programming and pretty much no knowledge of finance or the stock market.

![Application Screenshot](http://imageshack.us/a/img5/6245/portfoliotoolsmall.png "[Click here](http://seanduffy.co.uk/portfolio_tool/index.php) to view the project.")

Part of the course involves using a spreadsheet to construct a portfolio consisting of four stocks, and we were told to play around with the combination of stocks used and the weighting applied to each of them, i.e. what percentage of our total investment we put into each stock. Creating a spreadsheet is a good way to learn something about how the data in the portfolio is analysed, however after doing it once it becomes a very tedious process, having to manually download CSV files of the data for each of the stock prices from Yahoo finance and place them into the right position in the spreadsheet every time we wanted to try another combination.

To make this process more streamlined, I decided to create a PHP web application with the same basic functionality of this spreadsheet. Instead of manually fetching CSV files and pasting things into a spreadsheet, I was now able to enter the symbols for four securities and a decimal fraction representing the weighting of each one, click a button, and all the calculations would be done for me. I shared this with the other people taking the course via the forums and some said they found it useful and used it to make the peer-assessment part of the course more bearable and less error prone than manually dealing with a spreadsheet.

My application fetches the required CSV files from Yahoo Finance for the year 2011, and for every day calculates the cumulative percentage return and the current value of this stock position according to the weighting assigned to it. It then calculates the total value of the portfolio throughout the year and the percentage return for each day. It analyses the portfolio by calculating the annual percentage return, average daily return, the standard deviation of the daily return and finally the Sharpe Ratio of the portfolio. These were all simple calculations that just mimic the calculations performed in our spreadsheets.

To provide some visualisation, I also decided to create a dynamic graph of the cumulative returns of each of the stocks, plotted along with the SPY benchmark. For this I decided to go with [Google Charts](https://developers.google.com/chart/interactive/docs/index), which works very well. It lets you plot all kinds of highly customisable javascript charts, with some interactive functionality such as being able to hover the mouse pointer over a point on a line and see the value of the graph at that point.

To put this all together into a usable interface I used [Bootstrap](http://twitter.github.io/bootstrap/), which is of course heavily used, but gets the job done and is ideal for a project like this, being a quick and easy layout that is functional and also looks good.I wanted to keep this a one-page thing but at the same time there was a lot of data to be shown, so the tabs in Bootstrap were very handy for grouping together the relevant tables.

So here it is, the first example of something I've built that I'm sharing on my blog. It wasn't very difficult to build and of course its uses are limited due to the lack of features. Nevertheless I'm sure anyone taking Computational Investing will find use for it and it can serve as an example of something I've created and managed to get to a stage where it could be deployed and used by people other than myself. Thanks for reading and I hope you enjoyed my first project post, you might expect to see more in the not too distant future.
