---
title:  "Part 2: Building the \"Tweets of a Native Son\" Archive (jq and regular expressions)"
date:   2016-11-07 16:53:00 -0500
categories: 
comments: 
layout: single
author_profile: false
read_time: true
---

In [Part 1](http://melaniewalsh.org/2016/11/05/building-tweets-of-a-native-son-part1.html), I explained how I "hydrated" 17 million tweets that mentioned "Ferguson" from August and November 2014 by using [twarc](https://github.com/DocNow/twarc) and how I generated summaries for these collections (# of tweets and users, top hashtags, top URLs, top image URLS, etc.) using [twarc-report](https://github.com/pbinkley/twarc-report). But how and where does James Baldwin fit into the picture?

In this post, I'm going to talk about what Twitter metadata looks like (spoiler alert: it's pretty kooky) and how I reshaped the metadata to find only tweets that mentioned James Baldwin by using [jq](https://stedolan.github.io/jq/), a command-line utility for filtering JSON data.

---
<b>

Twitter metadata is wild. Every single tweet carries with it an enormous amount of information. Even a tweet as seemingly meaningless as ":poop:" carries with it not just the "text" (:poop:) of the tweet but also many other metadata fields such as:

* when the tweet was created
* how many times the tweet has been favorited or retweeted
* what language the tweet was written in
* which user wrote the tweet
* when the user created his or her account
* the user's profile description and profile picture and profile background color
* the user's location
* how many people follow the user
* how many people the user follows
* how many tweets the user has ever favorited
* how many tweets the user has ever sent

...and much, much more.[^1]

Here's just a glimpse of a single tweet from the August archive, which goes on for 96 lines:

![alt text](/images/json1.jpg)

As a tweet gets more complex---a reply to another user with a hashtag and a URL or a retweet with an image---the metadata gets even bigger and richer.

This richness makes the metadata wonderful for research purposes, allowing us to investigate all kinds of questions, but it also makes the data difficult to work with. If we want to extract just the tweets that mention James Baldwin, the nested structure of the JSON data (which you can learn more about [here](http://www.json.org/)) makes that a tricky task.

This is where [jq](https://stedolan.github.io/jq/) comes in, a command-line utility for reshaping JSON data. With jq, you can extract information from particular fields ("text," "coordinates," retweet_count," etc.) even when those fields are nested within other fields. You can even output the JSON data to a flat CSV file.[^2] For my purposes, I extracted only the tweets that mentioned James Baldwin by performing the filter operation `select()` on the `.text` field of the tweets, combined with a regular expressions string match for "James Baldwin" `test("James Baldwin")`:  

```
jq -c "select(.text | test(\"James Baldwin\"))" tweets.json > jamesbaldwin.json
```

This operation returned 1,697 tweets that mentioned "James Baldwin" from the August Ferguson tweet collection. But that's only when "James Baldwin" was spelled correctly with proper capitalization and spacing. So I decided to expand the search to collect other variations of his name without regard for capitalization and spacing, as well as permitting just a first initial and even misspellings that may have accidentally dropped the "d" from his name (#JamesBaldwin; J BALDWIN; james baldwin, James Balwin, etc.) :

```
jq -c "select(.text | test(\"J(ames|) ?Bald?win\";\"i\"))" tweets.json > jamesbaldwin.json
```

This operation returned an increased **<big>1,839</big>** tweets from the August collection and **<big>1,393</big>** tweets from the November collection. I experimented with an even more expansive search for simply “Baldwin,” which returned 3,410 tweets, but too many of them referenced a “Baldwin” not related to the literary James of interest, picking up instead on users’ last names, the actor Alec Baldwin, etc.

These **<big>3,232</big>** tweets from August and November quantitatively confirm scholars' claims---among them, Eddie S. Glaude and William J. Maxwell---that Baldwin is and was a leading literary voice in the burgeoning #BlackLivesMatter movement, since it proves that James Baldwin was being invoked and talked about on Twitter in the aftermath of Ferguson.

Yet the James Baldwin conversation represents less than **one-percent** of the total Twitter conversation in either dataset, which  serves as a tempering reminder that the scholarly sense of what is dominant in the larger cultural conversation may be skewed by scholarly newsfeeds. These numbers may even seem small enough to dismiss the case for Baldwin’s prominence on Twitter. But when cross-compared to other prominent black writers, Baldwin is far and away the most invoked. The words “James Baldwin” appear more in the August collection than “Claudia Rankine” (416), “Langston Hughes” (281), “Assata Shakur” (130), “Ta-Nehisi Coates” (129), “Toni Morrison” (72), “Teju Cole” (55), “Richard Wright” (50), “Ralph Ellison” (49), and “Amiri Baraka” (10) combined.  

But why? Why does Baldwin appear so much more frequently than other black writers? What about his style, insights, or legacy resonates in this particular historical moment and on this particular platform?

These are the literary questions that I will seek to answer in future posts through close-reading and further investigation of the data. But for now, I'll just share an overview of the Ferguson-Baldwin data produced using some twarc utilities and twarc-report. Check out the most popular retweets, hashtags, URLs, and image URLs below.


# **August Baldwin Tweet Archive**
---

|                                          |               |    |        |
|------------------------------------------|---------------|----|--------|
| **Tweets**:                                    | 1,839          |    |        |
| **Users**:                                    | 1,753          |    |        |
|  |               |    |        |
| **Has Hashtag**:                              | 1,169 (63.57%) |    |        |
| **Hashtags**:                                 | 115           |    |        |
|         |               |    |        |
| **Has URL**:                                  | 609 (33.12%)  |    |        |
| **URLs**:                                     | 166           |    |        |
|          |               |    |        |
| **Has Image URL**:                            | 47 (2.56%)    |    |        |
| **Image URLs**:                               | 18            |    |        |
|         |               |    |        |
| **Retweets**:                                 | 1,327 (72.16%) |    |        |
| **Geo**:                                      | 11 (0.60%)    |    |        |
| |
| **Earliest Tweet**:                                 2014-08-11 04:16:44 UTC 

<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">&quot;To be a Negro in this country and to be relatively conscious is to be in a rage almost all the time. ” ― James Baldwin <a href="https://twitter.com/hashtag/Ferguson?src=hash">#Ferguson</a></p>&mdash; Renaissance Man (@cjfluker) <a href="https://twitter.com/cjfluker/status/498684414483001344">August 11, 2014</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>
| |
| **Latest Tweet**:                                   | 2014-08-27 12:46:48 UTC |

<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">&#39;This Fight Begins In The Heart&#39;: Reading James Baldwin As Ferguson Seethes : NPR <a href="http://t.co/iLyNSrgwFZ">http://t.co/iLyNSrgwFZ</a></p>&mdash; AC De Lion (@anydel) <a href="https://twitter.com/anydel/status/504610983055081472">August 27, 2014</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>


| **Total Duration**:                                 | 16 days, 8:30:04     |
| 

**Top 10 Retweets:**

<b>

<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">&quot;To be Black and conscious in America is to be in a constant state of rage.&quot; - James Baldwin <a href="https://twitter.com/hashtag/Ferguson?src=hash">#Ferguson</a></p>&mdash; zellie (@zellieimani) <a href="https://twitter.com/zellieimani/status/499871572023586816">August 14, 2014</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script> 


<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">&quot;To be a Negro in this country and to be relatively conscious is to be in a rage almost all the time.&quot; —James Baldwin <a href="https://twitter.com/hashtag/Ferguson?src=hash">#Ferguson</a></p>&mdash; Crystal Kayiza (@c_kayiza) <a href="https://twitter.com/c_kayiza/status/498832276667793408">August 11, 2014</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>                  




<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">My new article on <a href="https://twitter.com/hashtag/Ferguson?src=hash">#Ferguson</a>, <a href="https://twitter.com/hashtag/MikeBrown?src=hash">#MikeBrown</a>, systemic racism and James Baldwin; if of interest, please share.<a href="http://t.co/DxhX3gCnnF">http://t.co/DxhX3gCnnF</a></p>&mdash; Musa Okwonga (@Okwonga) <a href="https://twitter.com/Okwonga/status/500008972016156672">August 14, 2014</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>


 <blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">if you&#39;re following <a href="https://twitter.com/hashtag/Ferguson?src=hash">#Ferguson</a>, watch this essential <a href="https://twitter.com/hashtag/JamesBaldwin?src=hash">#JamesBaldwin</a> testimony in June 1963: <a href="https://t.co/EVTTXgp82s">https://t.co/EVTTXgp82s</a></p>&mdash; Jose Antonio Vargas (@joseiswriting) <a href="https://twitter.com/joseiswriting/status/501231389333667842">August 18, 2014</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>



<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">&quot;This fight begins in the heart&quot;: <a href="https://twitter.com/LailaLalami">@LailaLalami</a> on reading James Baldwin as Ferguson seethes: <a href="http://t.co/pwErhUga3Z">http://t.co/pwErhUga3Z</a></p>&mdash; NPR Books (@nprbooks) <a href="https://twitter.com/nprbooks/status/501866250973478912">August 19, 2014</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>



<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">‘Not everything that is faced can be changed, but nothing can be changed until it is faced.’ - James Baldwin <a href="https://twitter.com/hashtag/FERGUSON?src=hash">#FERGUSON</a></p>&mdash; sandrine. (@drineee) <a href="https://twitter.com/drineee/status/503726050258325505">August 25, 2014</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>



<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr"><a href="http://t.co/mFvaZuMAIw">http://t.co/mFvaZuMAIw</a> Teju Cole&#39;s beautiful &amp; lacerating piece on James Baldwin, the &quot;black body&quot; &amp; the white gaze, <a href="https://twitter.com/hashtag/Ferguson?src=hash">#Ferguson</a> &amp; beyond.</p>&mdash; Joyce Carol Oates (@JoyceCarolOates) <a href="https://twitter.com/JoyceCarolOates/status/503278563056156673">August 23, 2014</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">A quote from James Baldwin in a PSA on <a href="https://twitter.com/hashtag/Ferguson?src=hash">#Ferguson</a> that aired during last night’s <a href="https://twitter.com/hashtag/VMAs?src=hash">#VMAs</a> WATCH: <a href="http://t.co/X0Q7Zs2z3y">http://t.co/X0Q7Zs2z3y</a> <a href="http://t.co/VyMthSXw6c">pic.twitter.com/VyMthSXw6c</a></p>&mdash; SPLC (@splcenter) <a href="https://twitter.com/splcenter/status/503947612299755520">August 25, 2014</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">&quot;But black people raise their children as a rehearsal for danger.” -James Baldwin <a href="https://twitter.com/hashtag/Ferguson?src=hash">#Ferguson</a></p>&mdash; Salamishah Tillet (@salamishah) <a href="https://twitter.com/salamishah/status/502105003033894912">August 20, 2014</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">&quot;White people think that childhood is a rehearsal for success. White people think of themselves as safe.&quot; -James Baldwin <a href="https://twitter.com/hashtag/Ferguson?src=hash">#Ferguson</a></p>&mdash; Salamishah Tillet (@salamishah) <a href="https://twitter.com/salamishah/status/502104900164386816">August 20, 2014</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>
         
<br>         
                                                                                        
|------------------------------:|----------------------------------------------------------|
| **Top Hashtags:**                |                                                                                         |      |
|      |
| 1. ferguson    							  | 1,093 |                                                                                     
| 2. jamesbaldwin  							 | 122  |                                                                                  
| 3. vmas     								 | 84   |                                                                                         
| 4. lookdifferent 								| 61   |                                                                                     
| 5. mikebrown    | 53   |                                                                                      
| 6. nmos14  | 28   |                                                                                           
| 7. vmawards  | 17   |                                                                                         
| 8. books   | 15   |                                                                                           
| 9. vmas2014  | 15   |                                                                                         
| 10. moralmonday | 15   |                                                                                                                                                                                         |      |
|      |
| **Top URLs:**                    |  |                                                                                        |      |
|      |
| 1. <https://www.youtube.com/watch?v=kXwVnYGJ_Cw>  | 73   |                                                    
| 2.  <http://www.newyorker.com/books/page-turner/black-body-re-reading-james-baldwins-stranger-village> | 61   |
| 3. <http://n.pr/1lfM1Ej>    | 59   |                                                                          
| 4. <http://sp.lc/VOarbH> | 49   |                                                                             
| 5. <http://n.pr/1rstgvg> | 33   |                                                                             
| 6. <http://wp.me/p4Rl2x-aCX> | 27   |                                                                         
| 7. <http://esqm.ag/6015W6MW> | 23   |                                                                         
| 8. <https://twitter.com/drgoddess/status/503726211621982208>  | 15   |                                        
| 9. <http://j.mp/1p3a2t0> | 15   |                                                                             
| 10. <http://n.pr/VFtghp>  | 11   |                                                                                                                                                                               |      |
|      |
| **Top Image URLs**:  |                                                                                                    |      |
|      |
| 1.	[![alt text](http://pbs.twimg.com/media/Bv5Mng5CIAAdKqx.jpg)](http://pbs.twimg.com/media/Bv5Mng5CIAAdKqx.jpg) | 15   |                                       
| 2. 	![alt text](http://pbs.twimg.com/media/Bv2YYDuIgAIrMx1.jpg) | 6    |                                       
| 3. 	![alt text](http://pbs.twimg.com/media/BvSVjOhCYAAp4HO.jpg)  | 5    |                                      
| 4. 	![alt text](http://pbs.twimg.com/media/BvsNlfPCAAEE-4I.jpg)   | 4    |                                     
| 5. 	![alt text](http://pbs.twimg.com/media/BvdepJJCIAASmnF.jpg) | 2    |                                       
| 6. 	![alt text](http://pbs.twimg.com/media/BvfXPJ6CMAET-7x.jpg)   | 2    |                                     
| 7. 	![alt text](http://pbs.twimg.com/media/Bv5hrs5IAAEJ-j9.png) | 2    |                                       
| 8. 	![alt text](http://pbs.twimg.com/media/Bu_9kkZIgAAQr4J.jpg)  | 1    |                                      
| 9. 	![alt text](http://pbs.twimg.com/media/BvVH43QIQAA80d-.jpg)  | 1    |                                      
| 10. 	![alt text](http://pbs.twimg.com/media/BvVgszMIgAAsEUz.jpg) | 1    |                                       

<br>

# **November Baldwin Archive**
***

|                                  |               |    |        |
|----------------------------------|---------------|----|--------|
| **Tweets**:                            | 1,393          |    |        |
| **Users**:                            | 1,231          |    |        |
|  |               |    |        |
| **Has Hashtag**:                      | 952 (68.34%)  |    |        |
| **Hashtags**:                         | 113           |    |        |
|  |               |    |        |
| **Has URL**:                          | 388 (27.85%)  |    |        |
| **URLs**:                             | 203           |    |        |
|   |               |    |        |
| **Has Image URL**:                    | 213 (15.29%)  |    |        |
| **Image URLs**:                       | 47            |    |        |
| |               |    |        |
| **Retweets**:                         | 987 (70.85%)  |    |        |
| **Geo**:                              | 11 (0.79%)    |    |        |
| |
| **Earliest Tweet**:                         | 2014-11-12 05:38:56 UTC |

<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">&quot;It is certain, in any case, that ignorance, allied with power, is the most ferocious enemy justice can have.&quot; ~ James Baldwin~ || <a href="https://twitter.com/hashtag/Ferguson?src=hash">#Ferguson</a></p>&mdash; Dante Boykin (@DanteB4u) <a href="https://twitter.com/DanteB4u/status/532407171867480064">November 12, 2014</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>
| |
| **Latest Tweet (Retweet)**:                           | 2014-12-10 04:08:08 UTC |

<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">&quot;If I love you, I have to make you conscious of the things you do not see.&quot; James Baldwin <a href="https://twitter.com/hashtag/icantbreathe?src=hash">#icantbreathe</a> <a href="https://twitter.com/hashtag/ferguson?src=hash">#ferguson</a> <a href="https://t.co/OKyGqNu5HX">https://t.co/OKyGqNu5HX</a></p>&mdash; Laurenellen McCann!! (@elle_mccann) <a href="https://twitter.com/elle_mccann/status/542393298833256449">December 9, 2014</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

| **Total Duration**:                         | 27 days, 22:29:12     |

<b>

**Top 10 Retweets:**

<b>

<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">James Baldwin quoted for Mike Brown. Union Square <a href="https://twitter.com/hashtag/Ferguson?src=hash">#Ferguson</a> demo <a href="http://t.co/u23WRicZR8">pic.twitter.com/u23WRicZR8</a></p>&mdash; Molly Crabapple (@mollycrabapple) <a href="https://twitter.com/mollycrabapple/status/537045590300188672">November 25, 2014</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">&quot;To be black in America is to be in a constant state of rage.&quot;<br><br>-James Baldwin <a href="https://twitter.com/hashtag/MikeBrown?src=hash">#MikeBrown</a> <a href="https://twitter.com/hashtag/FergusonTheRoot?src=hash">#FergusonTheRoot</a> <a href="https://twitter.com/hashtag/Ferguson?src=hash">#Ferguson</a></p>&mdash; Courtney Thornton (@courteroy_) <a href="https://twitter.com/courteroy_/status/537077232599330816">November 25, 2014</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">We live in &quot;a civilization which has always glorified violence--unless the Negro had the gun.&quot;--James Baldwin circa 1963 <a href="https://twitter.com/hashtag/Ferguson?src=hash">#Ferguson</a></p>&mdash; Jose Antonio Vargas (@joseiswriting) <a href="https://twitter.com/joseiswriting/status/537136943318831105">November 25, 2014</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">&quot;To be black and conscious in america is a constant state of rage&quot; - James Baldwin<a href="https://twitter.com/hashtag/noblackjusticenoblackfriday?src=hash">#noblackjusticenoblackfriday</a><a href="https://twitter.com/hashtag/Ferguson?src=hash">#Ferguson</a></p>&mdash; Gbenga Akinnagbe (@GbengaAkinnagbe) <a href="https://twitter.com/GbengaAkinnagbe/status/537130288787517442">November 25, 2014</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">My article on <a href="https://twitter.com/hashtag/Ferguson?src=hash">#Ferguson</a> and <a href="https://twitter.com/hashtag/MikeBrown?src=hash">#MikeBrown</a>, with an important quote from James Baldwin. If of interest, please share.  <a href="http://t.co/S5DsNyJAmG">http://t.co/S5DsNyJAmG</a></p>&mdash; Musa Okwonga (@Okwonga) <a href="https://twitter.com/Okwonga/status/537188928923918336">November 25, 2014</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">James Baldwin&#39;s prophetic words in 1960<a href="https://twitter.com/hashtag/Ferguson?src=hash">#Ferguson</a> <a href="https://twitter.com/hashtag/BlackLivesMatter?src=hash">#BlackLivesMatter</a> <a href="https://twitter.com/hashtag/FergusionDecision?src=hash">#FergusionDecision</a> <a href="http://t.co/G4KX6bRdfF">pic.twitter.com/G4KX6bRdfF</a></p>&mdash; Rahiel Tesfamariam (@RahielT) <a href="https://twitter.com/RahielT/status/537122331597225984">November 25, 2014</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">&quot;To be a Negro in this country and to be relatively conscious is to be in a rage almost all the time.&quot; —James Baldwin <a href="https://twitter.com/hashtag/Ferguson?src=hash">#Ferguson</a></p>&mdash; Crystal Kayiza (@c_kayiza) <a href="https://twitter.com/c_kayiza/status/498832276667793408">August 11, 2014</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">James Baldwin: &quot;The law is meant to be my servant and not my master, still less my torturer and my murderer.&quot; <a href="https://twitter.com/hashtag/Ferguson?src=hash">#Ferguson</a></p>&mdash; Nikhil Goyal (@nikhilgoya_l) <a href="https://twitter.com/nikhilgoya_l/status/537071543579594753">November 25, 2014</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">“To be a Negro in this country and to be relatively conscious is to be in a rage almost all the time. ” – James Baldwin <a href="https://twitter.com/hashtag/Ferguson?src=hash">#Ferguson</a></p>&mdash; Yasiel Plug (@Ketchcast) <a href="https://twitter.com/Ketchcast/status/537074466262507520">November 25, 2014</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">&quot;To be a Negro in this country and to be relatively conscious is to be in a rage almost all the time.&quot; - James Baldwin <a href="https://twitter.com/hashtag/Ferguson?src=hash">#Ferguson</a></p>&mdash; BlackHistoryStudies (@BlkHistStudies) <a href="https://twitter.com/BlkHistStudies/status/538014453934333952">November 27, 2014</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

<b>

|                              |                                                                                                                                 |     |
|------------------------------|---------------------------------------------------------------------------------------------------------------------------------|-----|
| |
| **Top Hashtags**:                | 
| | |                                                                                                                  |     |
| 1.                            ferguson                                                                                                                        | 836 |
| 2.                            mikebrown                                                                                                                       | 196 |
| 3.                            blacklivesmatter                                                                                                                | 174 |
| 4.                            jamesbaldwin                                                                                                                    | 104 |
| 5.                           noblackjusticenoblackfriday                                                                                                     | 48  |
| 6.                           fergusiondecision                                                                                                               | 45  |
| 7.                           icantbreathe                                                                                                                    | 34  |
| 8.                            fergusontheroot                                                                                                                 | 23  |
| 9.                            hiphoped                                                                                                                        | 22  |
| 10.                           standup                                                                                                                         | 20  |
|                              |                                                                                                                                 |     |
| **Top URLs**:                     | 
| |                                                                                                                                |     |
| 1.                            <http://Advocate.com>                                                                                                           | 54  |
| 2.                           <http://www.cbc.ca/thesundayedition/features/2014/11/30/post-11/>                                                               | 33  |
| 3.                            <http://esqm.ag/6013t1KF>                                                                                                       | 23  |
| 4.                            <http://shar.es/1XEN2s>                                                                                                         | 18  |
| 5.                           <http://www.advocate.com/politics/2014/11/25/5-james-baldwin-quotes-foreshadowed-ferguson>                                      | 18  |
| 6.                            <http://www.agos.com.tr/tr/yazi/9893/fergusondan-yuksekovaya-james-baldwinin-ruhuyla>                                           | 16  |
| 7.                            <http://www.neontommy.com/news/2014/12/ferguson-and-blacklivesmatter-illustrate-how-james-baldwin-s-words-continue-resonate-mo> | 11  |
| 8.                            <http://bit.ly/1yTCKna>                                                                                                         | 11  |
| 9.                            <http://bit.ly/1B9TCdI>                                                                                                         | 10  |
| 10.                           <http://www.newstatesman.com/politics/2014/08/amid-tear-gas-and-arrests-reporters-ferguson-we-must-not-lose-sight-mike-brown>   | 9   |
|                              |                                                                                                                                 |     |
| **Top Image URLs**:    |                                                                                                                                 |     |
| |
| 1.                            ![alt text](http://pbs.twimg.com/media/B3P4HZ-IQAAVvS1.jpg)                                                                     | 45  |
| 2.                            ![alt text](http://pbs.twimg.com/media/B3Q96NpIMAAnv04.jpg)                                                                     | 44  |
| 3.                            ![alt text](http://pbs.twimg.com/media/B3UWme1IIAItKda.png)                                                                     | 23  |
| 4.                            ![alt text](http://pbs.twimg.com/media/B4L2sPYCQAIJlSO.jpg)                                                                     | 19  |
| 5.                            ![alt text](http://pbs.twimg.com/media/B4auO9rCAAA_f_m.png)                                                                     | 9   |
| 6.                            ![alt text](http://pbs.twimg.com/media/B3jBSQHCQAAY8ek.jpg)                                                                     | 8   |
| 7.                            ![alt text](http://pbs.twimg.com/media/B3T5Iy-CYAEZ_Gi.jpg)                                                                     | 7   |
| 8.                            ![alt text](http://pbs.twimg.com/media/B4audKGCAAAT34u.png)                                                                     | 5   |
| 9.                            ![alt text](http://pbs.twimg.com/media/B3Zjf4GCEAA_eTx.jpg)                                                                     | 4   |
| 10.                           ![alt text](http://pbs.twimg.com/media/B3esOS8IIAAlLbS.jpg)                                                                     | 4   |



[^1]: If you're interested in finding out more about the structure of Twitter metadata, check out [Twitter's documentation here](https://dev.twitter.com/overview/api/tweets).

[^2]: For a full jq tutorial, I recommend Matthew Lincoln's very helpful ["Reshaping JSON with jq"](http://programminghistorian.org/lessons/json-and-jq).



