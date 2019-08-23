---
title:  "Things That The U.S. Presidents Described as \"Great\" in Their Inaugural Addresses"
date:   2017-02-01 16:29:00 -0500
categories: 
comments: 
layout: single
author_profile: false
read_time: true
---

For the February 2017 meeting of the [Digital Approaches Reading Group](http://sites.wustl.edu/darg) (DARG), which I help co-convene at WashU, we explored 58 Presidential Inaugural Addresses as a common dataset --- in the hopes of collectively showcasing and experimenting with different DH methodologies and tools. I was personally curious about a tiny word that I suspected might have big(ly?) implications: the word "great."

President Trump concluded his 2017 Inaugural Address with his now trademark phrase "Make America Great Again":
>"Together, we will make America strong again. We will make America wealthy again. We will make America proud again. We will make America safe again. And yes, together, we will make America *great* again."

The adjective "great" is one of the cornerstones of Trump's rhetoric, showing up in speeches and tweets to describe things as various as policy meetings, The Apprentice, the threat of CNN, and the proposed Mexican border wall:


<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">Great meeting with CEOs of leading U.S. health insurance companies who provide great healthcare to the American people. <a href="https://t.co/s2NMVMvQq3">pic.twitter.com/s2NMVMvQq3</a></p>&mdash; Donald J. Trump (@realDonaldTrump) <a href="https://twitter.com/realDonaldTrump/status/836261209540288513">February 27, 2017</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">FAKE NEWS media knowingly doesn&#39;t tell the truth. A great danger to our country. The failing <a href="https://twitter.com/nytimes">@nytimes</a> has become a joke. Likewise <a href="https://twitter.com/CNN">@CNN</a>. Sad!</p>&mdash; Donald J. Trump (@realDonaldTrump) <a href="https://twitter.com/realDonaldTrump/status/835325771858251776">February 25, 2017</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">I am reading that the great border WALL will cost more than the government originally thought, but I have not gotten involved in the.....</p>&mdash; Donald J. Trump (@realDonaldTrump) <a href="https://twitter.com/realDonaldTrump/status/830405706255912960">February 11, 2017</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">Arnold Schwarzenegger isn&#39;t voluntarily leaving the Apprentice, he was fired by his bad (pathetic) ratings, not by me. Sad end to great show</p>&mdash; Donald J. Trump (@realDonaldTrump) <a href="https://twitter.com/realDonaldTrump/status/838016045222854656">March 4, 2017</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

I wanted to explore how previous Presidents had used the word "great" before him. Could I find a historical precedent for this adjective and/or a trajectory of its shifting ideological value?

# Methodology

I used the Python module TextBlob, specifically its part-of-speech tagger and ngrams function, to isolate all the nouns that came immediately before or after the word "great" in every speech. Here are the top 10 things that were most commonly described as "great" across all inaugural addresses and the top Presidents who used the word:



| | word      | total # in all addresses |
|:-----------:|:-------------------------:|:--:|
| 1 | nation    | 10                      |
| 2 | people    | 8                       |
| 3 | interests | 6                       |
| 4 | body      | 4                       |
| 5 | objects   | 4                       |
| 6 | wealth    | 3                       |
| 7 | evil      | 3                       |
| 8 | object    | 3                       |
| 9 | republic  | 3                       |
| 10 | responsibilities  | 3                       |


<b>

<b>

|    | President | total # of "great" as noun modifier |
|:----:|:------------------------:|:----:|
| 1  | James Monroe           | 35 |
| 2  | William Henry Harrison | 16 |
| 3  | William McKinley       | 13 |
| 4  | Woodrow Wilson         | 10 |
| 5  | Andrew Garfield        | 10 |
| 6  | Calvin Coolidge        | 10 |
| 7  | Benjamin Harrison      | 9  |
| 8  | Franklin D. Roosevelt  | 8  |
| 9  | William Howard Taft    | 8  |
| 10 | James Pierce           | 8  |
| 11 | Ruherford B. Hayes     | 6  |
| 12 | George W. Bush         | 6  |
| 13 | Warren G. Harding      | 6  |
| 14 | George H. W. Bush      | 6  |
| 15 | Richard Nixon          | 6  |
| 16 | James Buchanan         | 6  |
| 17 | Ulysses S. Grant       | 5  |
| 18 | Ronald Reagan          | 5  |
| 19 | Dwight D. Eisenhower   | 5  |
| 20 | Martin Van Buren       | 5  |
| 21 | Barack Obama           | 4  |
| 22 | Donald Trump           | 4  |

<b>

Surprisingly, Donald Trump didn't even crack the top 10!

I played around with visualizing this data in a number of ways, which included a dendrogram and a radial sunburst.

![Alt text](/images/dendrogram.svg)

![Alt text](/images/sunburst.svg)

They're pretty, but ultimately I don't think they show us all that much about the data. So I also created a semantic network to try and understand which "great" things were connecting which Presidents. I used NetworkX, Gephi, and the Sigma.JS plugin to create this force-directed semantic network and this accompanying [interactive web version](/network/index.html).

![Alt text](/images/gephi_network.svg)

So did the tiny word "great" end up having the big implications that I suspected when I first set out? Well, yes and no. I was surprised to discover, though I really shouldn't have been, that "great" is an incredibly bland, abstract word, which is used to describe a whole lot of bland, abstract concepts like "people," "interests," and "objects." "Nation," the word most commonly described as "great," connects Presidents as disparate as Barack Obama, Richard Nixon, Ulysses S. Grant, Ruherford B. Hayes, James Monroe, Andrew Garfield, George H. W. Bush, Theodore Roosevelt, Franklin D. Roosevelt, and Jimmy Carter. In other words, "great" didn't reveal as many ideological insights as I first expected. It's largely used as rhetorical fluff and filler, a vague hand-wavy intensifier.

But this lack of meaning *is* meaningful. It reveals even more clearly, to my mind, that Trump's "Make America Great Again" slogan is one big empty rhetorical illusion. What exactly does "great" mean? What exactly makes America "great"? A lot is hidden inside this bland banality, as George Orwell would be the first to warn us. In his 1946 essay "Politics and the English Language," Orwell insists that some of the most insidious, violent politics "consist largely of euphemism, question-begging and sheer cloudy vagueness." 

It is curious, however, that Donald Trump is the only President to describe "America" as "great" (at least immediately before or after the word "America") and suggests that this slogan is a relatively unique coinage. It was much more common to refer to the "nation" or "people" or "republic" as "great" than to refer to "America" as "great," which perhaps suggests something about our increasingly globalized moment, in which distinguishing "America" from the rest of the world has become more of a routine necessity and, to some, particularly those in the Trump camp, an intense anxiety.


Seeing which Presidents are connected by which words is also rather curious, though I'm not entirely sure what to make of it. Donald Trump and George H. W. Bush are connected by the word "men." Ronald Reagan and Ulysses S. Grant are connected by "honor." Dwight D. Eisenhower, James Buchanan, and Andrew Garfield are all connected by "evil" (Buchanan also dropped the plural "great evil*s*"). William McKinley, George W. Bush, and Richard Nixon are all connected by "responsibilities." James Monroe and John Adams are connected by "satisfaction." And Harry S. Truman, Bill Clinton, and George Washington aren't connected to anyone at all.

Feel free to explore the network yourself and see what other kinds of connections and/or oddities you can find. I will conclude here with a list of the best/weirdest "great" things in the Inaugural Addresses according to the U.S. Presidents according to me. 

| | top weirdest "great" things as decreed by me in no particular order     | President |
|:-----------:|:-------------------------:|:--:|
| 1 | blotches    |    Warren G. Harding                 |
| 2 | parties   |      George H. W. Bush                  |
| 3 | dread |               William Henry Harrison        |
| 4 | bulwark      |        William Henry Harrison                |
| 5 | annoyance  |          James Monroe            |
| 6 | scheme    |   James Pierce                   |
| 7 | inlets      |    James Monroe                  |
| 8 | hands   |      Andrew Jackson              |
| 9 | satisfaction  |     John Adams                |
| 10 | rebellion  |      Ulysses S. Grant                 |


<b>

Check out the source code for the project [here](https://github.com/melaniewalsh/inaugural_addresses).
  

