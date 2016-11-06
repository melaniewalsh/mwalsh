---
layout: post
title:  "Building the Baldwin Tweet Archive: Part 1 (twarc and twarc-report)"
date:   2016-11-05 14:56:56 -0500
categories: twitter, tweets
comments: true
---

So my project "Tweets of a Native Son" examines the way that Twitter conversations about Ferguson and the #BlackLivesMater movement invoke the literary author James Baldwin. What's my archive? How did I build it?

Tweets can be ephemeral little stinkers. Since Twitter's Search API only allows you to collect tweets from the last 1-2 weeks, foresight is huge when building a Twitter archive. Thankfully, Ed Summers had the foresight to start collecting tweets that mentioned "Ferguson" (upper or lowercase; with or without hashtag) in the weeks and months following Michael Brown's shooting and, just as important, the generosity to share them [openly](https://archive.org/details/ferguson-tweet-ids). Though Twitter’s Terms of Service does not allow bulk distribution of Twitter data, it does allow the distribution of tweet “ids,” which are unique identifiers that get assigned to every tweet and can be used to retroactively access the full tweet metadata, a process called "hydrating" that can be performed with a command line Python tool like [twarc](https://github.com/DocNow/twarc), which was also created by Ed Summers. Yeah, Ed rules.

So the first step in building my Baldwin Tweet archive was hydrating the Ferguson tweet collections from both August and November:


    mwalsh@ada:~/ferguson-tweet-ids/data$ gunzip ids.txt.gz
    mwalsh@ada:~/ferguson-tweet-ids/data$ nohup twarc.py --hydrate ids.txt > tweets.json &


Since Twitter’s API rate limit only allows requests for up to 72,000 tweets per hour, this process took approximately 8 and 9 days, respectively. The utility ["twarc-report,"](https://github.com/pbinkley/twarc-report) created by Peter Binkley, allows me to generate a helpful, summarizing overview of these collections (# of tweets and users, top hashtags, top URLs, top images, etc.):


    mwalsh@ada:~/ferguson-tweet-ids/data$ ~/twarc-report/reportprofile.py -o text tweets.json
    mwalsh@ada:~/ferguson-indictment-tweet-ids/data$ ~/twarc-report/reportprofile.py -o text tweets.indictment.json


# **August Ferguson Collection**
---

|                        |                                  |
|------------------------|----------------------------------|
| Tweets:                  | 10,441,785                         |
| Users:                  | 1,596,104                          |
| User percentiles:       | █▂▁▁▁▁▁▁▁▁                       |
|                        | [71, 10, 5, 3, 3, 2, 2, 2, 2, 2] |
| | |
| Has hashtag:            | 6,898,701 (66.07%)                 |
| Hashtags:               | 99,695                            |
| Hashtags percentiles:   | █▁▁▁▁▁▁▁▁▁                       |
|                        | [98, 1, 0, 0, 0, 0, 0, 0, 0, 0]  |
| | |
| Has URL:                | 3,317,445 (31.77%)                 |
| URLs:                   | 664,691                           |
| URLs percentiles:       | █▁▁▁▁▁▁▁▁▁                       |
|                        | [78, 6, 3, 2, 2, 2, 2, 2, 2, 2]  |
| | |
| Has Image URL:          | 1,593,403 (15.26%)                 |
| Image URLs:             | 134,431                           |
| Image URLs percentiles: | █▁▁▁▁▁▁▁▁▁                       |
|                        | [87, 4, 2, 1, 1, 1, 1, 1, 1, 1]  |
| | |
| Retweets:               | 7,411,799 (70.98%)                 |
| Geo:                    | 74,678 (0.72%)                    |
| Earliest:               | 2014-08-10 22:44:33 UTC          |
| Latest:                 | 2014-08-27 15:15:50 UTC          |
| Duration:               | 16 days, 16:31:07                 |

|                                                             |         |
|-------------------------------------------------------------|---------|
| # Top hashtags:     █▂▁▁▁▁▁▁▁▁                                |         |
|                                                             |         |
| 1. ferguson                                                    | 6,422,131 |
| 2. mikebrown                                                   | 583,141  |
| 3. michaelbrown                                                | 158,552  |
| 4. justiceformikebrown                                         | 84,061   |
| 5. tcot                                                        | 70,702   |
| 6. gaza                                                        | 70,338   |
| 7. stl                                                         | 58,662   |
| 8. handsupdontshoot                                            | 47,126   |
| 9. darrenwilson                                                | 40,091   |
| 10. fergusonshooting                                            | 31,643   |
|                                                             |         |
|  Top URLs:  █▃▂▂▂▁▁▁▁▁                                       |         |
|                                                             |         |
| 1. <http://new.livestream.com/accounts/9035483/events/3271930> | 37,917   |
| 2. <http://bzfd.it/VDlPH8>                                     | 12,906   |
| 3. <http://thebea.st/1l8uDRK>                                  | 10,773   |
| 4. <http://bbc.in/1uS3tSd>                                   | 9,841    |
| 5. <http://www.livestream.com/activistworldnewsnow>          | 8,276    |
| 6. <http://wapo.st/1sXk4Sj>                                    | 7,535    |
| 7. <http://es.pn/1AvncY9>                                      | 7,514    |
| 8. <https://vine.co/v/M3rWtqnrHi9>                             | 6,771    |
| 9. <http://ind.pn/1qjd6lO>                                     | 6,366    |
| 10. <http://ow.ly/ADgCF>                                        | 5,909    |
|                                                             |         |
| Top Image URLs: █▃▃▃▂▂▂▁▁▁                                  |         |
|                                                             |         |
| 1. ![alt text](http://pbs.twimg.com/media/BvSVYWKIIAAGPhB.jpg) | 21,899   |
| 2. ![alt text](http://pbs.twimg.com/media/BvROlxsIUAA632n.jpg) | 10,486   |
| 3. ![alt text](http://pbs.twimg.com/media/BvUSCd4CMAEiZ-u.jpg) | 10,319   |
| 4. ![alt text](http://pbs.twimg.com/media/BvSlV60CUAAEPhU.jpg) | 9,029    |
| 5. ![alt text](http://pbs.twimg.com/media/BvaPNHTIIAE6UIi.jpg) | 7,956    |
| 6. ![alt text](http://pbs.twimg.com/media/BvYUwzIIMAAiH62.jpg) | 7,586    |
| 7. ![alt text](http://pbs.twimg.com/media/Bu9zJKeIIAAa4Jt.jpg) | 6,842    |
| 8. ![alt text](http://pbs.twimg.com/media/Bu9bSPRCIAAnntQ.jpg) | 6,223    |
| 9. ![alt text](http://pbs.twimg.com/media/Bu-lkolCAAIwyN0.jpg) | 5,998    |
| 10. ![alt text](http://pbs.twimg.com/media/Buu2CQGIUAEqJPU.jpg) | 5,195    |

<br>

# **November Ferguson Collection**
***

|                        |                                 |
|------------------------|---------------------------------|
| Tweets:                  | 7,868,540                         |
| Users:                  | 1,761,950                         |
| User percentiles:       | █▂▁▁▁▁▁▁▁▁                      |
|                        | [68, 9, 5, 4, 2, 2, 2, 2, 2, 2] |
|                        |                                 |
| Has hashtag:            | 4,567,256 (58.04%)                |
| Hashtags:               | 110,097                          |
| Hashtags percentiles:   | █▁▁▁▁▁▁▁▁▁                      |
|                        | [97, 1, 1, 0, 0, 0, 0, 0, 0, 0] |
| | |
| Has URL:                | 3,514,869 (44.67%)                |
| URLs:                   | 927,040                          |
| URLs percentiles:       | █▁▁▁▁▁▁▁▁▁                      |
|                        | [73, 6, 3, 3, 3, 3, 3, 3, 3, 3] |
| | |
| Has Image URL:          | 1,465,857 (18.63%)                |
| Image URLs:             | 191,684                          |
| Image URLs percentiles: | █▁▁▁▁▁▁▁▁▁                      |
|                        | [83, 5, 3, 1, 1, 1, 1, 1, 1, 1] |
| | |
| Retweets:               | 5,004,081 (63.60%)                |
| Geo:                    | 51,007 (0.65%)                   |
| Earliest:               | 2014-11-11 22:17:06 UTC         |
| Latest:                 | 2014-12-10 05:15:31 UTC         |
| Duration:               | 28 days, 6:58:25                |

|                                                             |         |
|-------------------------------------------------------------|---------|
| Top hashtags: █▁▁▁▁▁▁▁▁▁                                    |         |
|                                                             |         |
| 1. ferguson                                                    | 3,969,513 |
| 2. mikebrown                                                   | 188,976  |
| 3. ericgarner                                                  | 178,139  |
| **4. blacklivesmatter**                                           | **151,749**  |
| 5. fergusondecision                                            | 118,405  |
| 6. michaelbrown                                                | 105,607  |
| 7. tcot                                                        | 99,477   |
| 8. darrenwilson                                                | 89,154   |
| 9. icantbreathe                                                | 89,000   |
| 10. shutitdown                                                  | 45,296   |
|                                                             |         |
|                                                             |         |
| Top URLs: █▇▅▃▃▃▂▂▁▁                                        |         |
|                                                             |         |
| 1. <http://cnn.it/1tAZkMJ>                                     | 11,592   |
| 2. <http://nbcnews.to/12fXQ5f>                                 | 10,644   |
| 3. <http://ble.ac/1B376rD>                                     | 9,848    |
| 4. <http://invst.rs/7f2xJB>                                    | 8,609    |
| 5. <http://nyp.st/1vjOX47>                                     | 8,535    |
| 6. <http://cbsn.ws/1vzqR5B>                                    | 8,097    |
| 7. <http://bit.ly/1d5qTtO>                                     | 7,460    |
| 8. <http://vine.co/v/On1x6iUuwxK>                              | 7,396    |
| 9. <http://on.rt.com/80mggq>                                   | 7,038    |
| 10. <http://bit.ly/1vFrMUx>                                     | 7,028    |
|                                                             |         |
| Top Image URLs: █▇▇▆▅▅▄▄▃▁                                  |         |
|                                                             |         |
| 1. ![alt text](http://pbs.twimg.com/media/B3qe80-CEAAWikm.jpg) | 11,453   |
| 2. ![alt text](http://pbs.twimg.com/media/B3a_FyOCAAAmLxp.jpg) | 10,907   |
| 3. ![alt text](http://pbs.twimg.com/media/B3S-EmbIcAEfEUB.jpg) | 10,681   |
| 4. ![alt text](http://pbs.twimg.com/media/B3QPEpBCAAAD1c_.jpg) | 10,004   |
| 5. ![alt text](http://pbs.twimg.com/media/B3ZzWTjIAAAkHwC.jpg) | 9,299    |
| 6. ![alt text](http://pbs.twimg.com/media/B3Z-LUNCAAA_1P4.jpg) | 9,190    |
| 7. ![alt text](http://pbs.twimg.com/media/B3YnVqyIgAA_8o9.jpg) | 8,484    |
| 8. ![alt text](http://pbs.twimg.com/media/B3ginLnCIAEXnYD.jpg) | 7,870    |
| 9. ![alt text](http://pbs.twimg.com/media/B3pa9UrIEAAhrmj.jpg) | 7,310    |
| 10. ![alt text](http://pbs.twimg.com/media/B3SlDtxIIAARDT1.jpg) | 5,824    |

<br>
From the 13,480,000 ids in the August collection, I was able to hydrate 10,441,785 tweets. From the 15,080,078 ids in the November collection, I was able to hydrate 7,868,540 tweets. If you're wondering where the heck all those missing tweets went, so am I. If a Twitter user deletes his/her tweets between the tweet publication and the time of hydration, then that tweet gets lost forever. Ed Summers thinks this is a [lowkey ethical move](https://medium.com/on-archivy/on-forgetting-e01a2b95272#.jlm9fifcj) on Twitter's part, allowing users the right to be forgotten, even though they don't state this outright. Still, 7,868,540 is a heckuva lot of missing tweets, and I hope to theorize these silences and disappearances more fully in later posts.

For now, however, I'll conclude Part 1 by saying that twarc is an awesome tool for creating Twitter archives if you know even a little bit about Python/the command line (though I should mention that Ed Summers is currently leading a project called ["Documenting the Now"](http://www.docnow.io/) which aims to develop an even easier-to-use tool that requires no programming skills whatsoever) and twarc-report is a small but powerful utility for getting a sense of the contours of one's dataset, and it can even reveal key patterns and critical insights on its own . For instance, from the twarc-report summaries alone, we can see #BlackLivesMatter emerging into the mainstream Ferguson conversation. From August 10, 2014 to August 27, 2014, roughly the two weeks after Michael Brown’s shooting, the hashtag #BlackLivesMatter doesn't even make the Top 10, but by November 11, 2014 to December 10, 2014, roughly the month after Darren Wilson’s non-indictment, #BlackLivesMatter has rocketed to No. 4. These reports indicate that the fourth months between August 10 and December 10 represent a crucial moment in the rise and circulation of the #BlackLivesMatter movement, as has been suggested by scholars and activists elsewhere.

In Part 2, I will discuss how I narrowed these collections to only the tweets that mention James Baldwin (using jq and regular expressions) and what the twarc-reports of these smaller James Baldwin collections reveal.

 {% if page.comments %} 
 <div id="disqus_thread"></div>
<script>

/**
*  RECOMMENDED CONFIGURATION VARIABLES: EDIT AND UNCOMMENT THE SECTION BELOW TO INSERT DYNAMIC VALUES FROM YOUR PLATFORM OR CMS.
*  LEARN WHY DEFINING THESE VARIABLES IS IMPORTANT: https://disqus.com/admin/universalcode/#configuration-variables*/
/*
var disqus_config = function () {
this.page.url = melaniewalsh.org;  // Replace PAGE_URL with your page's canonical URL variable
this.page.identifier = PAGE_IDENTIFIER; // Replace PAGE_IDENTIFIER with your page's unique identifier variable
};
*/
(function() { // DON'T EDIT BELOW THIS LINE
var d = document, s = d.createElement('script');
s.src = '//melaniewalsh.disqus.com/embed.js';
s.setAttribute('data-timestamp', +new Date());
(d.head || d.body).appendChild(s);
})();
</script>
<noscript>Please enable JavaScript to view the <a href="https://disqus.com/?ref_noscript">comments powered by Disqus.</a></noscript>
                                
  {% endif %} 


