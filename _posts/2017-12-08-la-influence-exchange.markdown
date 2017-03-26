---
layout:     post
title:      "Los Angeles Influence Exchange"
subtitle:   "Money, Power, and Opportunity"
date:       2014-12-08 12:00:00
author:     "Pauline"
header-img: "img/post-bg-piggy-bank.jpg"
permalink:  /:year/:month/la-influence-exchange
comments:   true 
---
>Money can’t buy love, but it improves your bargaining position...

is a quote Christopher Marlowe, an Elizabethan tragedian playwright, who had his share of woes in love and finances. Money is an alluding factor in politics and complicates accountability. Money, power and love (aka the popularity contest portion) push contenders to the top. Without the right balance of resources and public perceived integrity, no one is winning any races and if you don’t win races, then there are “friends” no longer. Ethics guidelines and reporting for elections and public officials attempt to light up the “influence exchange” (analogy to stock exchange).

Relevant questions for accountability seekers:

What is being exchanged for influence on public decisions? i.e. money, property, resources, nepotism, good will, publicity, etc.
Who (individuals, companies, and institutions) are asking for influence?
Why are these entities asking for influence?
What are the important factors of the influence exchange, such as timing, money, quantity of influence benefits (the getting in the door factor), deliverer of benefits (many entities pay lobbying firms or the benefit is presented by a 3rd party)?
An open dataset from the Los Angeles City Open Data portal is available from the City Ethic Commission (CEC) on lobbying activities and includes: (1) list of registered lobbyists, (2) payment made by clients to registered lobbying firms, (3) payments made by client made to city projects, and (4) graph of ethics payments by lobbying firm. The City of Los Angeles Municipal Lobbying Ordinance requires disclosure, record keeping, and disclosure of attempts to influence City Officials by services, donations, fundraising events, and anything falling within the definition of  the law, §§ 48.01. Given my interest in the public sector and accountability, I thought this might be a good place to start poking around and get to know some data.

At initial analysis, these datasets require cleaning, transformation and aggregation to become ore informative. Even for smaller set of information and metrics, time is required to understand its content. I thought for a naive second that I would only spend a few hours on the datasets to get insights. The Los Angeles Lobbying/Ethics datasets cannot paint the entire picture of “influence exchanges” and all its activities and related transactions in the City. It is a start to seeking relative comparisons and major players in politics:

Covers 2 reporting years (2013-2014)
Records cannot be condensed/expanded in a meaningful way, where the names of firms and clients do not provide immediate insight into lobbying activities in LA City
Monetary value of payments create comparison metrics and does not paint the full relationship between City Officials, Lobbying Firm, Clients, or Projects
The main problem with these datasets are the ability to derive meaning from the numbers. So, to start, what do we know? 2013 Ambruster Goldsmith & Delvac LLP was paid over $3M in lobbying money to Los Angeles City Officials. As an better way to explain the situation to myself, I created and populated a category field in the dataset. First, I tried to pull North American Industry Codes (NAICS) by company name or scraping provided websites (also an mostly “empty” column in the dataset) but these techniques did not complete the records. Next, matching records by characters and strings are not ideal. Here is when I had flashbacks of data collecting, while I was at a consulting gig in my early 20s. Finally, I got a little obsessed and completed the exercise with manually entry (a lot of manual entry). Although tedious, it did help familiarized myself with the data. The chosen categories were intended to build insight into grouping and visualization of the data in R, see throughout the post & scripts in Python and R on my GitHub.

The data with categories can be downloaded: LA Open Data – Lobbying Firm Payments with Categories. It was actually quite interesting to go through the dataset details. Some additional insights:

Graphs at the top of this post: This 2 year dataset shows the potential for a simple trend analysis over time to uncover patterns of behaviors by lobbying firms and/or their clients. Trends can be broken out by category/industry, and client or lobbying firm. Also, when external information can be matched with behaviors then the dataset becomes more powerful.
The largest group of lobbying clients (entities influencing City Officials) are related to Real Estate and Development (“Real Estate & Dev”). Real Estate and Development range the gambit of single/multiple family homes and commercial investors, developers, and property managers. During the search, client names and some internet investigations did not help to break out the larger category. So partly the huge “Real Estate & Dev” category is the result of “human error” in this dataset, but most importantly the result of poor data collection and public information. See graphs below.
LACity_lobby_catLobby_Firm_Cat_noRD

Sharing Economy vs. Transportation Services. A big stake fight over territory between car/ride sharing companies and taxi and car services. These categories include a few other related companies and services but it looks like the “Sharing Economy” (includes rides/ car sharing and hotel services) and “Transportation Services” (taxis, shuttles, bus services) lobbying fees have not changed significantly in the last two years. Transportation Services pay more than 7 times the lobbying fees to the City of LA than Sharing Economy, but Sharing Economy company count doubled in the last year, see comparison below.
LACity_Lobbying_Cat_SEvTS


REPORT YEAR	CATEGORY	TOTAL PAID	COUNT CLIENTS
2013	Sharing Economy	$9689	6
2013	Transportation Services	$75426	55
2014	Sharing Economy	$13870	12
2014	Transportation Services	$74696	58
Read the next post in the LA Influence Exchange: Location, Location, Location, mapped points of projects that lobbyists paid to influence.

