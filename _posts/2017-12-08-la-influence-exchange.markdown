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
<blockquote>
<p style="text-align: center;">Money can't buy love, but it improves your bargaining position - Christopher Marlowe</p>
</blockquote>
<img style="float:right" src="/img/LACity_Lobby_Overtime_All-300x144.png" width="350"/><img style="float:left" src="/img/LACity_Lobby_OverTime_RDout-300x144.png" width="350"/>
<p>The Elizabethan tragedian playwright Christopher Marlowe embodied the contradition between money and love. Money is a consistent alluding factor in politics and complicates accountability. Ethics guidelines exists to create a balance between political office and working for the common good, which is an illusive principle. These guidelines require reporting of certain types of interactions with public officials as a means to shine a light on "<strong>influence exchange</strong>" (analogy to stock exchange).</p>
<p>What questions are eludicated about lobbyists with the at the City of Los Angeles open data? If you're an accountability seeker than you might ask these questions:</p>
<ul>
<li>What is being exchanged for influence on public decisions, such as money, property, resources, jobs, or zoning and land use mechanims?</li>
<li>Who are asking for influence, including individuals, companies, and institutions?</li>
<li>What are the important factors of the influence exchange, such as timing, money, quantity of influence benefits (the getting in the door factor), deliverer of benefits (many entities pay lobbying firms or the benefit is presented by a 3rd party)?</li>
<li>Can donations by lobbyist be tied with specific events, such as building or elections, and infer intent between the exchange?</li>
</ul>
<p>An open dataset from the <a href="https://data.lacity.org/" style="color:orange">Los Angeles City Open Data portal</a> is available from the City Ethic Commission (CEC) on lobbying activities and includes: (1) list of registered lobbyists, (2) payment made by clients to registered lobbying firms, (3) payments made by client made to city projects, and (4) graph of ethics payments by lobbying firm. The City of Los Angeles Municipal Lobbying Ordinance requires disclosure, record keeping, and disclosure of attempts to influence City Officials by services, donations, fundraising events, and anything falling within the definition of  the law, <a href="http://ethics.lacity.org/PDF/laws/law_mlo.pdf" style="color:orange">§§ 48.01</a>. Given my interest in the public sector and accountability, I thought this might be a good place to start poking around and get to know some data.</p>
<p>At initial analysis, these datasets require cleaning, transformation and aggregation to become ore informative. Even for smaller set of information and metrics, time is required to understand its content. I thought for a naive second that I would only spend a few hours on the datasets to get insights. The Los Angeles Lobbying/Ethics datasets cannot paint the entire picture of "influence exchanges" and all its activities and related transactions in the City. It is a start to seeking relative comparisons and major players in politics:</p>
<ul>
<li>Covers 2 reporting years (2013-2014)</li>
<li>Records cannot be condensed/expanded in a meaningful way, <em>where the names of firms and clients do not provide immediate insight into lobbying activities in LA City</em></li>
<li>Monetary value of payments create comparison metrics and does not paint the full relationship between City Officials, Lobbying Firm, Clients, or Projects</li>
</ul>
<p>The main problem with these datasets are the ability to derive meaning from the numbers. So, to start, what do we know? <a href="https://data.lacity.org/A-Well-Run-City/2013-Ethics-Commision-Payments-Chart/9477-ettm" style="color:orange">2013 Ambruster Goldsmith &amp; Delvac LLP was paid over $3M in lobbying money to Los Angeles City Officials</a>. As an better way to explain the situation to myself, I created and populated a category field in the dataset. First, I tried to pull North American Industry Codes (NAICS) by company name or scraping provided websites (also an mostly "empty" column in the dataset) but these techniques did not complete the records. Next, matching records by characters and strings are not ideal. Here is when I had flashbacks of data collecting, while I was at a consulting gig in my early 20s. Finally, I got a little obsessed and completed the exercise with manually entry (a lot of manual entry). Although tedious, it did help familiarized myself with the data. The chosen categories were intended to build insight into grouping and visualization of the data in R, see throughout the post &amp; scripts in Python and R on <a href="https://github.com/PowChow/WhenThereIsData" style="color:orange">my GitHub repo</a>.</p>
<p>The data with categories can be downloaded: <a href="http://www.whenthereisdata.com/wp-content/uploads/2014/12/Lobby_Pay_Categories.csv" style="color:orange">LA Open Data - Lobbying Firm Payments with Categories</a>. It was actually quite interesting to go through the dataset details. Some additional insights:</p>
<ul>
<li><span style="text-decoration: underline;">Graphs at the top of this post</span>: This 2 year dataset shows the potential for a simple trend analysis over time to uncover patterns of behaviors by lobbying firms and/or their clients. Trends can be broken out by category/industry, and client or lobbying firm. Also, when external information can be matched with behaviors then the dataset becomes more powerful.</li>
<li>The largest group of lobbying clients (entities influencing City Officials) are related to Real Estate and Development ("Real Estate &amp; Dev"). Real Estate and Development range the gambit of single/multiple family homes and commercial investors, developers, and property managers. During the search, client names and some internet investigations did not help to break out the larger category. So partly the huge "Real Estate &amp; Dev" category is the result of "human error" in this dataset, but most importantly the result of poor data collection and public information. <span style="text-decoration: underline;">See graphs below</span>.</li>
</ul>
<img style="float:right" src="/img/LACity_lobby_cat-300x214.png" width="350"/>
<img style="float:right" src="/img/Lobby_Firm_Cat_noRD-300x214.png" width="350"/>

<ul>
<li><span style="text-decoration: underline;">Sharing Economy vs. Transportation Services</span>. A big stake fight over territory between car/ride sharing companies and taxi and car services. These categories include a few other related companies and services but it looks like the "Sharing Economy" (includes rides/ car sharing and hotel services) and "Transportation Services" (taxis, shuttles, bus services) lobbying fees have not changed significantly in the last two years. Transportation Services pay more than 7 times the lobbying fees to the City of LA than Sharing Economy, but Sharing Economy company count doubled in the last year, see comparison below.</li>
</ul>

<p><img style="float:center" src="/img/LACity_Lobbying_Cat_SEvTS-300x158.png" width="500"/></p>

<p align="center"><b>Lobbying Firm Payments: Sharing vs. Transportation</b></p>

| Report Year  | Category | Total Paid  | Count Clients |
|:--------|:--------:|:-------:|-------:|
| 2013   | Share Econ| $9,689   | 6  |
| 2013   | Transport | $75,426 | 55   |
| 2014   | Share Econ| $13,870   | 12 |
| 2014   | Transport | $74,696   | 58 |

<p>Read the next post in the LA Influence Exchange: <a href="http://www.whenthereisdata.com/?p=161">Location, Location, Location</a>, mapped points of projects that lobbyists paid to influence.</p>
