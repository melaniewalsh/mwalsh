---
layout: post
title:  "Building the Baldwin Tweet Archive: Part 1"
date:   2016-11-05 14:56:56 -0500
categories: twitter, tweets
---

So my project "Tweets of a Native Son" examines the way that Twitter conversations about Ferguson and the #BlackLivesMater movement invoke the literary author James Baldwin. What's my archive? How did I build it?

Tweets can be ephemeral little stinkers. Since Twitter's Search API only allows you to collect tweets from the last 1-2 weeks, foresight is huge when building a Twitter archive. Thankfully, Ed Summers had the foresight to start collecting tweets that mentioned "Ferguson" (upper or lowercase; with or without hashtag) in the weeks and months following Michael Brown's shooting and, just as important, the generosity to share them [openly](https://archive.org/details/ferguson-tweet-ids). Though Twitter’s Terms of Service does not allow bulk distribution of Twitter data, it does allow the distribution of tweet “ids,” which are unique identifiers that get assigned to every tweet and can be used to retroactively access the full tweet metadata, a process called "hydrating" that can be performed with a command line Python tool like [twarc](https://github.com/DocNow/twarc), which was also created by Ed Summers. Yeah, Ed rules.

So the first step in building my Baldwin Tweet archive was hydrating the Ferguson tweet collections from both August and November:

```python
mwalsh@ada:~/ferguson-tweet-ids/data$ gunzip ids.txt.gz
mwalsh@ada:~/ferguson-tweet-ids/data$ nohup twarc.py --hydrate ids.txt > tweets.json &
```
Since Twitter’s API rate limit only allows requests for up to 72,000 tweets per hour, this process took approximately 8 and 9 days, respectively. The utility ["twarc-report,"](https://github.com/pbinkley/twarc-report) created by Peter Binkley, allows me to generate a helpful, summarizing overview of these collections (# of tweets and users, top hashtags, top URLs, top images, etc.):

```python
mwalsh@ada:~/ferguson-tweet-ids/data$ ~/twarc-report/reportprofile.py -o text tweets.json
mwalsh@ada:~/ferguson-indictment-tweet-ids/data$ ~/twarc-report/reportprofile.py -o text tweets.indictment.json
```

# August Ferguson Collection

Count:             10441785
Users:              1596104
User percentiles: █▂▁▁▁▁▁▁▁▁
                  [71, 10, 5, 3, 3, 2, 2, 2, 2, 2]
Has hashtag:        6898701 (66.07%)
Hashtags:             99695
Hashtags percentiles: █▁▁▁▁▁▁▁▁▁
                  [98, 1, 0, 0, 0, 0, 0, 0, 0, 0]
Has URL:            3317445 (31.77%)
URLs:                664691
URLs percentiles: █▁▁▁▁▁▁▁▁▁
                  [78, 6, 3, 2, 2, 2, 2, 2, 2, 2]
Has Image URL:      1593403 (15.26%)
Image URLs:          134431
Image URLs percentiles: █▁▁▁▁▁▁▁▁▁
                  [87, 4, 2, 1, 1, 1, 1, 1, 1, 1]
Retweets:           7411799 (70.98%)
Geo:                  74678 (0.72%)
Earliest:         2014-08-10 22:44:43 UTC
Latest:           2014-08-27 15:15:50 UTC
Duration:         16 days, 16:31:07

Top users:        █▅▄▄▃▃▃▂▂▁
   5438 eprince1110
   4516 kvayozone
   4188 gerfingerpoken
   4160 gerfingerpoken2
   4131 MissouriSentina
   4078 WarOnFerguson
   3983 MCTV419
   3641 carolynsbuddy
   3608 kavn
   3447 sierramike320

Top hashtags:     █▂▁▁▁▁▁▁▁▁
6422131 ferguson
 583141 mikebrown
 158552 michaelbrown
  84061 justiceformikebrown
  70702 tcot
  70338 gaza
  58662 stl
  47126 handsupdontshoot
  40091 darrenwilson
  31643 fergusonshooting
  
Top URLs:         █▃▂▂▂▁▁▁▁▁
  37917 [http://new.livestream.com/accounts/9035483/events/3271930]
  12906 [http://bzfd.it/VDlPH8]
  10773 [http://thebea.st/1l8uDRK]
   9841 [http://bbc.in/1uS3tSd]
   8276 [http://www.livestream.com/activistworldnewsnow]
   7535 [http://wapo.st/1sXk4Sj]
   7514 [http://es.pn/1AvncY9]
   6771 [https://vine.co/v/M3rWtqnrHi9]
   6366 [http://ind.pn/1qjd6lO]
   5909 [http://ow.ly/ADgCF]

Top Image URLs:   █▃▃▃▂▂▂▁▁▁

  21899 ![alt text](http://pbs.twimg.com/media/BvSVYWKIIAAGPhB.jpg)
  10486 ![alt text](http://pbs.twimg.com/media/BvROlxsIUAA632n.jpg)
  10319 ![alt text](http://pbs.twimg.com/media/BvUSCd4CMAEiZ-u.jpg)
   9029 ![alt text](http://pbs.twimg.com/media/BvSlV60CUAAEPhU.jpg)
   7956 ![alt text](http://pbs.twimg.com/media/BvaPNHTIIAE6UIi.jpg)
   7586 ![alt text](http://pbs.twimg.com/media/BvYUwzIIMAAiH62.jpg)
   6842 ![alt text](http://pbs.twimg.com/media/Bu9zJKeIIAAa4Jt.jpg)
   6223 ![alt text](http://pbs.twimg.com/media/Bu9bSPRCIAAnntQ.jpg)
   5998 ![alt text](http://pbs.twimg.com/media/Bu-lkolCAAIwyN0.jpg)
   5195 ![alt text](http://pbs.twimg.com/media/Buu2CQGIUAEqJPU.jpg)
   
# November Ferguson Collection

Count:              7868540

Users:              1761950

User percentiles: █▂▁▁▁▁▁▁▁▁
                  [68, 9, 5, 4, 2, 2, 2, 2, 2, 2]
                  
                  
Has hashtag:        4567256 (58.04%)

Hashtags:            110097

Hashtags percentiles: █▁▁▁▁▁▁▁▁▁
                  [97, 1, 1, 0, 0, 0, 0, 0, 0, 0]
                  
Has URL:            3514869 (44.67%)

URLs:                927040

URLs percentiles: █▁▁▁▁▁▁▁▁▁
                  [73, 6, 3, 3, 3, 3, 3, 3, 3, 3]
                  
Has Image URL:      1465857 (18.63%)

Image URLs:          191684

Image URLs percentiles: █▁▁▁▁▁▁▁▁▁
                  [83, 5, 3, 1, 1, 1, 1, 1, 1, 1]
                  
Retweets:           5004081 (63.60%)

Geo:                  51007 (0.65%)

Earliest:         2014-11-11 22:17:06 UTC

Latest:           2014-12-10 05:15:31 UTC

Duration:         28 days, 6:58:25


Top users:        █▇▄▂▂▂▁▁▁▁|
|---|---|
   6351| gerfingerpoken
   6031 |gerfingerpoken2
   4783 |UnitePink
   4193 |OwlsAsylum
   4126 |Tigerfists88
   3814 |deray
   3804 |HotNostrilsrFun
   3692 |staciemritchie
   3619 |Ferguson_Now
   3615 |surrealintel


Top hashtags:     █▁▁▁▁▁▁▁▁▁|
|---|---|
3969513| ferguson
188976| mikebrown
178139| ericgarner
151749| blacklivesmatter
118405| fergusondecision
105607| michaelbrown
99477| tcot
89154| darrenwilson
89000| icantbreathe
45296| shutitdown
  
  
|Top URLs:         █▇▅▃▃▃▂▂▁▁ |
|---|---|
11592 |[http://cnn.it/1tAZkMJ]
10644 |[http://nbcnews.to/12fXQ5f]
9848 |[http://ble.ac/1B376rD]
8609 |[http://invst.rs/7f2xJB]
8535 |[http://nyp.st/1vjOX47]
8097 |[http://cbsn.ws/1vzqR5B]
7460 |[http://bit.ly/1d5qTtO]
7396 |[http://vine.co/v/On1x6iUuwxK]
7038 |[http://on.rt.com/80mggq]
7028 |[http://bit.ly/1vFrMUx]
   
|Top Image URLs:   █▇▇▆▅▅▄▄▃▁ |
|---|---|
|11453|![alt text](http://pbs.twimg.com/media/B3qe80-CEAAWikm.jpg)|
|10907 | ![alt text](http://pbs.twimg.com/media/B3a_FyOCAAAmLxp.jpg)|
|10681 | ![alt text](http://pbs.twimg.com/media/B3S-EmbIcAEfEUB.jpg)|
|10004 | ![alt text](http://pbs.twimg.com/media/B3QPEpBCAAAD1c_.jpg)|
|9299 | ![alt text](http://pbs.twimg.com/media/B3ZzWTjIAAAkHwC.jpg)|
|9190 | ![alt text](http://pbs.twimg.com/media/B3Z-LUNCAAA_1P4.jpg)|
|8484 | ![alt text](http://pbs.twimg.com/media/B3YnVqyIgAA_8o9.jpg)|
|7870 | ![alt text](http://pbs.twimg.com/media/B3ginLnCIAEXnYD.jpg)|
|7310 | ![alt text](http://pbs.twimg.com/media/B3pa9UrIEAAhrmj.jpg)|
|5824 | ![alt text](http://pbs.twimg.com/media/B3SlDtxIIAARDT1.jpg)|

| Top Image URLs      |
| ------------- |-------------| -----|
| col 3 is      | right-aligned | $1600 |
| col 2 is      | centered      |   $12 |
| zebra stripes | are neat      |    $1 |


From the 13,480,000 ids in the August collection, I was able to hydrate 10,441,785 tweets. From the 15,080,078 ids in the November collection, I was able to hydrate 7,868,540 tweets. If you're wondering, where the heck are all those missing tweets?!,that's a damn good question--one that Ed Summers has tackled here and one that I plan to theorize more fully in later blog posts.

For now, however, I'll conclude by saying that twarc-report is a terrific little tool for getting a sense of the contours of one's dataset and can help reveal key patterns. For instance, from this summary alone we can start to see the #BlackLivesMatter emerging into the mainstream Ferguson conversation. From August 10, 2014 to August 27, 2014, roughly the two weeks after Michael Brown’s shooting, the hashtag #BlackLivesMatter doesn't even appear in the Top 10 most frequent hashtags, but by November 11, 2014 to December 10, 2014, roughly the month after Darren Wilson’s non-indictment, #BlackLivesMatter emerges as the fourth most popular hashtag, indicating its gaining strength and circulation.


