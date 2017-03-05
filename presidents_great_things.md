---
layout: page
permalink: /presidents_great_things/
---
# **Things That The U.S. Presidents Described as "Great" in Their Inaugural Addresses**

For the February 2017 meeting of the Digital Approaches Reading Group (DARG) that I co-convene at WashU, we explored 58 Presidential Inaugural Addresses as a common dataset---in the hopes of showcasing and experimenting with different DH methodologies and tools. I was personally curious about a tiny word that I suspected might have big(ly?) implications: the word "great."

President Trump concluded his 2017 Inaugural Address with the trademark phrase "Make America Great Again." The adjective "great" is indeed one of the cornerstones of Trump's rhetorical style, showing up in speeches and tweets to describe things as various as policy meetings, The Apprentice, the threat of CNN, and the proposed Mexican border wall:


<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">Great meeting with CEOs of leading U.S. health insurance companies who provide great healthcare to the American people. <a href="https://t.co/s2NMVMvQq3">pic.twitter.com/s2NMVMvQq3</a></p>&mdash; Donald J. Trump (@realDonaldTrump) <a href="https://twitter.com/realDonaldTrump/status/836261209540288513">February 27, 2017</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">FAKE NEWS media knowingly doesn&#39;t tell the truth. A great danger to our country. The failing <a href="https://twitter.com/nytimes">@nytimes</a> has become a joke. Likewise <a href="https://twitter.com/CNN">@CNN</a>. Sad!</p>&mdash; Donald J. Trump (@realDonaldTrump) <a href="https://twitter.com/realDonaldTrump/status/835325771858251776">February 25, 2017</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">I am reading that the great border WALL will cost more than the government originally thought, but I have not gotten involved in the.....</p>&mdash; Donald J. Trump (@realDonaldTrump) <a href="https://twitter.com/realDonaldTrump/status/830405706255912960">February 11, 2017</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">Arnold Schwarzenegger isn&#39;t voluntarily leaving the Apprentice, he was fired by his bad (pathetic) ratings, not by me. Sad end to great show</p>&mdash; Donald J. Trump (@realDonaldTrump) <a href="https://twitter.com/realDonaldTrump/status/838016045222854656">March 4, 2017</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

I wanted to explore how previous Presidents had used the word "great" before him. Could I find a historical precedent for this adjective and/or a trajectory of its shifting ideological value?

#Methodology

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

But I also wanted to create a semantic network to more clearly understand which "great" things were connecting which Presidents. So I used NetworkX, Gephi, and the Sigma.JS plugin to create this [interactive force-directed network](/network/index.html). Some strange and surprising insights come to light through the data and visualizations.

For instance, Donald Trump is the only President who described "America" as "great" (at least immediately before or after the word "America") which suggests that his trademark slogan is a relatively unique coinage. It was much more common to refer to the "nation" or "people" or "republic" as "great" than to refer to "America" as "great." What does this change mean? To speculate only briefly, I suspect the new specificity of "America" might have something to do with our increasingly globalized moment, in which distinguishing "America" from the rest of the world is a necessity and, to some, an intense anxiety.

There are also some surprising connections between the Presidents themselves. Donald Trump and George H. W. Bush are connected by the word "men." Ronald Reagan and Ulysses S. Grant are connected by "honor." Dwight D. Eisenhower, James Buchanan, and Andrew Garfield are all connected by "evil" (Buchanan also dropped the plural "great evils"). William McKinley, George W. Bush, and Richard Nixon are all connected by "responsibilities." James Monroe and John Adams are connected by "satisfaction." And Harry S. Truman, Bill Clinton, and George Washington aren't connected to anyone at all! 

Please feel free to explore the network and see what else you can find!
  
