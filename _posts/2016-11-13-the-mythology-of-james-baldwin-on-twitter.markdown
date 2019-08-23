---
title:  "\"The Mythology of James Baldwin on Twitter\""
date:   2016-11-13 16:29:00 -0500
categories: 
comments: 
layout: single
author_profile: false
read_time: true
---

_The following is a transcript from my paper "Tweets of a Native Son: The Mythology of James Baldwin on Twitter," which I gave at the [MMLA conference](http://www.luc.edu/mmla/convention/) on November 12. Huge thanks to Doug Knox from the [HDW](https://hdw.artsci.wustl.edu/) for helping me figure out how to wrangle Twitter data and to [Ed Summers from MITH](http://mith.umd.edu/people/person/ed-summers/) for generously sharing data, tools, and thoughtfulness._

---


|---|---|
![alt text](/images/tobeanegro.jpg) [By Ronald Wimberly](https://www.behance.net/gallery/23843777/Black-History-Month-in-Its-Own-Words) | ![alt text](/images/tobeblackandconscious.jpg) [By John Ira Jennings](http://jijennin70.tumblr.com/post/121885939190/finally-finished-this-baldwin-piece) [@JIJennings](https://twitter.com/jijennings?lang=en)|

<b>

<big>J</big>ames Baldwin is alive and well on Twitter, and literary scholars should be paying attention. Though Baldwin published his last two works in 1985, two years before his death, today he speaks anew on the popular social media platform—and I mean “anew” quite literally. Baldwin’s words are not simply being invoked, referenced, and quoted; they are also being edited, updated, and in some places wholly fabricated. Eddie S. Glaude Jr. and William J. Maxwell have both noted that Baldwin has become one of the leading literary voices of the #BlackLivesMatter movement, considered a clarifying prophetic muse of contemporary American race relations and politics, especially on Twitter, where, as the leading hashtag in #BlackLivesMatter reminds us, this movement largely began and continues to flourish. Both scholars have also asked why. Why Baldwin? Why now? “His words inspire on social media; his phrases speak from T-shirts; his face covers a throw pillow on Etsy,” Glaude writes in an [August _Time_ article](http://time.com/4457112/james-baldwin-eddie-glaude/). “But apart from his marketability—that people can use him as an avatar of supposed seriousness—what does Baldwin offer us in this moment? What does he force us, as Americans, to confront?” My paper seeks to answer these questions and investigate the relationship between Baldwin’s literary legacy and contemporary American racial politics by taking his words on social media seriously and by conducting a large-scale computational analysis of tweets. But why am I, as a literary scholar, taking tweets seriously? 

First, I’m doing so because I believe that social media data, which has exploded since the early 2000s, composes perhaps the most comprehensive account of readership and marginalia ever available and thus offers great if untapped potential for literary scholars. In his 1986 essay “First Steps Toward a History of Reading,” Robert Darnton lamented the difficulty of studying readership because “documents rarely show readers at work, fashioning meaning from texts” and because “few of them are rich enough to provide even indirect access to the cognitive and affective elements of reading” (7). But social media data offers precisely that kind of access, a kind of public diary of user’s thoughts and feelings. With over 313 million active users monthly and over 500 million tweets published per day, Twitter data offers literary critics an unprecedentedly wide look  at how readers beyond the the academy engage with literary works and their authors—how they talk about literature, feel about literature, and use literature in their daily lives to better understand the world around them. My perspective aligns with Lev Manovich’s concept of “cultural analytics” and the mission of the new journal [_Cultural Analytics_](http://culturalanalytics.org/), both of which advocate for a computational approach to the study of culture that takes advantage of the massive amounts of online user-generated content now available and that doesn’t “draw a boundary between (smaller) historical professional artifacts and (bigger) online digital content created by non-professionals”[^1] in the way that most digital humanities projects, especially literary-minded ones, generally do. Though exceptional literary works created by exceptional professionals have been the bread and butter of literary studies, I believe that user-generated content from non-professionals produced at these large scales can fundamentally change the way we study readership.

Second, Twitter holds particular significance for my study of Baldwin because it’s been the platform most fundamental to the growth of the #BlackLivesMatter movement and represents a rich conversation about race and politics in America conducted by ordinary citizens. The first and third most popular hashtags in Twitter’s ten-year history are, in fact, #Ferguson and #BlackLivesMatter, which, when measured last March, had been tweeted [27,200,000 times and 12,000,000 times](https://www.washingtonpost.com/news/the-switch/wp/2016/03/21/these-are-the-10-most-influential-hashtags-in-honor-of-twitters-birthday/), respectively. To investigate Baldwin’s relationship to these hashtags and these movements, my project thus takes as its archive two sets of tweets that were collected in the months following Michael Brown’s shooting in Ferguson, Missouri: 10,441,785 tweets that mentioned “Ferguson” (either upper or lowercase; with or without a hashtag) between August 10, 2014 and August 27, 2014, roughly the two weeks after the shooting; and 7,868,540 tweets that mentioned “Ferguson” between November 11, 2014 and December 10, 2014, roughly the month after Darren Wilson’s non-indictment.[^2]  These two snapshots represent, as Sarah J. Jackson and Brooke Foucault Welles have claimed in [their study of the hashtag #Ferguson](http://www.tandfonline.com/doi/full/10.1080/1369118X.2015.1106571), “national debates about American racism, police profiling and brutality, militarized responses to civil unrest, government corruption and criminal justice,” as well as the time period when the hashtag #BlackLivesMatter first emerged in a significant way and became popularized. Thus I’m framing my study of tweets that mention “Ferguson” as the crucial beginnings of the #BlackLivesMatter movement on Twitter.

<b>

|          |    |   |
|------------------------|----------------------------------|------|
| | **August 2014** | |**November 2014**
| | | |
| **Tweets:**                  | 10,441,785         | |7,868,540  
| **Users:**                  | 1,596,104            | |1,761,950 
| **Earliest Tweet:**               | 2014-08-10           | |2014-11-11  
| **Latest Tweet:**                 | 2014-08-27           | |2014-12-10 
| **Total Duration:**               | 16 days, 16:31:07                 | |28 days, 6:58:25 
|                                                             |         |
|-------------------------------------------------------------|---------|
|  **Top Hashtags:**                                  |         |      |       |
||||
| 1. ferguson                                                    | 6,422,131 || 1. ferguson                                                    | 3,969,513 |
| 2. mikebrown                                                   | 583,141  || 2. mikebrown                                                   | 188,976  | 
| 3. michaelbrown                                                | 158,552  || 3. ericgarner                                                  | 178,139  |
| 4. justiceformikebrown                                         | 84,061   || 4. **blacklivesmatter**                                         | **151,749** |
| 5. tcot                                                        | 70,702   || 5. fergusondecision                                            | 118,405  | 
| 6. gaza                                                        | 70,338   || 6. michaelbrown                                                | 105,607  |
| 7. stl                                                         | 58,662   || 7. tcot                                                        | 99,477   |
| 8. handsupdontshoot                                            | 47,126   || 8. darrenwilson                                                | 89,154   |
| 9. darrenwilson                                                | 40,091   || 9. icantbreathe                                                | 89,000   |
| 10. fergusonshooting                                            | 31,643   || 10. shutitdown                                                  | 45,296   |

<b>

After “hydrating” these 17 million tweets using a tool called [twarc](https://github.com/DocNow/twarc)---and “hydrating” basically just means retrieving the metadata for these tweets from the Twitter API[^3]---the next step was narrowing the archive to just the tweets that mention both “Ferguson” and “James Baldwin,” and indeed finding out whether these tweets even existed. So I performed a search for any variation of “J Baldwin” or “James Baldwin” (for example: #JamesBaldwin; J BALDWIN; james balwin, etc.) that appeared within the text of a tweet, which returned 1,839 tweets from the first August dataset and 1,393 tweets from the second November dataset.[^4]  These searches quantitatively confirm Glaude’s and Maxwell’s claims about Baldwin’s influence, chiefly that James Baldwin was being talked about on Twitter in the aftermath of Ferguson. 

And yet the James Baldwin conversation represents less than one-percent of the total conversation in either dataset, which serves as a tempering reminder that the scholarly sense of what is dominant in the larger cultural conversation may be skewed by scholarly newsfeeds. These numbers may even seem small enough to dismiss the case for Baldwin’s prominence on Twitter entirely. But when cross-compared to other prominent black writers, Baldwin is far and away the most invoked. The words “James Baldwin” (1,708 tweets) appear more in the August archive than “Claudia Rankine” (416), “Langston Hughes” (281), “Assata Shakur” (130), “Ta-Nehisi Coates” (129), “Toni Morrison” (72), “Teju Cole” (55), “Richard Wright” (50), “Ralph Ellison” (49), and “Amiri Baraka” (10) combined. As far as tweeted literary conversations go, the James Baldwin conversation is a substantial and dominant one.

So why does Baldwin appear so much more frequently than other black writers? What about his style, insights, or legacy resonates in this particular historical moment and on this particular platform? Though my larger long-term project seeks to answer these questions from a number of different angles, the first way I have tried to understand Baldwin’s influence is by analyzing the most popular tweets in the archive, the tweets with the highest “retweet_count,” a category that already conveniently exists in the Twitter metadata and records the number of times a tweet has been shared by another user on his or her own timeline, which often (but not always) suggests a kind of endorsement, and thus can be thought of as an index for community consensus about value and resonance.
	
---

<b>
	
# **Top 10 August Retweets:**

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

<b>

---

<b>

# **Top 10 November Retweets:**

<b>

[Tweet deleted]

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

[Tweet deleted]

<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">“To be a Negro in this country and to be relatively conscious is to be in a rage almost all the time. ” – James Baldwin <a href="https://twitter.com/hashtag/Ferguson?src=hash">#Ferguson</a></p>&mdash; Yasiel Plug (@Ketchcast) <a href="https://twitter.com/Ketchcast/status/537074466262507520">November 25, 2014</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">&quot;To be a Negro in this country and to be relatively conscious is to be in a rage almost all the time.&quot; - James Baldwin <a href="https://twitter.com/hashtag/Ferguson?src=hash">#Ferguson</a></p>&mdash; BlackHistoryStudies (@BlkHistStudies) <a href="https://twitter.com/BlkHistStudies/status/538014453934333952">November 27, 2014</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>
<b>

---
         
<br>

These lists immediately reveal that users most often invoke Baldwin through quotation. In fact, Twitter users even appear to have a meta-awareness of the influx of Baldwin quotations in the Ferguson conversation:
	 

<blockquote class="twitter-tweet" data-lang="en"><p lang="fr" dir="ltr">*insert James Baldwin quote* <a href="https://twitter.com/hashtag/Ferguson?src=hash">#Ferguson</a></p>&mdash; jefe💙🇭🇹 (@heLLobrOOklyn) <a href="https://twitter.com/heLLobrOOklyn/status/499767201826869249">August 14, 2014</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>
 
<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">I&#39;m really need ppl to chill with these James Baldwin quotes. I have no interest in being that woke right now <a href="https://twitter.com/hashtag/ferguson?src=hash">#ferguson</a></p>&mdash; Ashley Powell (@_APowPow) <a href="https://twitter.com/_APowPow/status/498925415025872896">August 11, 2014</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

These lists also reveal that the Baldwin users overwhelmingly invoke is the social critic James Baldwin, not the fiction writer James Baldwin. His essays, interviews, and debates are far and away the most referenced and quoted works, and in fact no quotations from his fiction appear in these lists. But I want to argue that Baldwin’s literary legacy is not unremembered. Instead I believe that Baldwin’s literary legacy is essential to his role as muse for the #BlackLivesMatter movement, and that his intellectual hybridity as both artist and activist is what makes him particularly attractive. Baldwin’s mythos as an imaginative novelist and artistic genius infuses his more aphoristic, more incisive, and thus more tweetable social criticism. 

Looking at which Baldwin quotes get retweeted most can give us a sense of how Baldwin’s Twitter readers respond to his texts—which texts, which styles, subjects, and tones resonate the most, and from which parts of Baldwin’s career. But what’s perhaps even more revealing for Baldwin’s readership and reception is not just when Baldwin is being quoted but when he is being _misquoted_, when Baldwin’s words get edited, updated, transformed, or sometimes even fabricated whole cloth by Twitter users, often outstripping real quotations in circulation and popularity. The focus of the rest of my paper today will be on such a misquotation, a particularly curious and widespread misquotation that continues to evolve and negotiate with its original form throughout the archive, ultimately even surpassing its original form in popularity.

This quote was originally excerpted from <a href="https://youtu.be/jNpitdJSXWY?t=43s">"The Negro in American Culture,"</a> a group discussion between Baldwin, Langston Hughes, Lorraine Hansberry, Emile Capouya, and Alfred Kazin that aired on the New York radio station WBAI-FM in January of 1961 and was later transcribed in the journal _CrossCurrents_ the following summer: “Well, the first difficulty is really so simple it’s usually overlooked: to be a Negro in this country and to be relatively conscious, is to be in a rage almost all the time.” The very first tweet that appears in the archive quotes from “The Negro in American Culture” verbatim, or at least directly from the transcript:
	
<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">&quot;To be a Negro in this country and to be relatively conscious is to be in a rage almost all the time. ” ― James Baldwin <a href="https://twitter.com/hashtag/Ferguson?src=hash">#Ferguson</a></p>&mdash; Renaissance Man (@cjfluker) <a href="https://twitter.com/cjfluker/status/498684414483001344">August 11, 2014</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

This accurate transcription of the quote appears as the second most popular tweet in the August archive, clearly resonating with Twitter users:

<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">&quot;To be a Negro in this country and to be relatively conscious is to be in a rage almost all the time.&quot; —James Baldwin <a href="https://twitter.com/hashtag/Ferguson?src=hash">#Ferguson</a></p>&mdash; Crystal Kayiza (@c_kayiza) <a href="https://twitter.com/c_kayiza/status/498832276667793408">August 11, 2014</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

But an inaccurate version of this quote is, astonishingly, over four times more popular than the accurate transcription of Baldwin’s words, making it the most popular tweet in the August archive: 

<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">&quot;To be Black and conscious in America is to be in a constant state of rage.&quot; - James Baldwin <a href="https://twitter.com/hashtag/Ferguson?src=hash">#Ferguson</a></p>&mdash; zellie (@zellieimani) <a href="https://twitter.com/zellieimani/status/499871572023586816">August 14, 2014</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

The most popular James Baldwin quote being invoked in the wake of Michael Brown’s death was thus never actually spoken by James Baldwin. Tellingly, the changes, omissions, and additions made to Baldwin’s words are not announced by brackets, ellipses, or paraphrase, but are instead smoothly and subtly elided. Even more evolutions appear in the November archive, again surpassing the original form in popularity.

<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">&quot;To be black in America is to be in a constant state of rage.&quot;<br><br>-James Baldwin <a href="https://twitter.com/hashtag/MikeBrown?src=hash">#MikeBrown</a> <a href="https://twitter.com/hashtag/FergusonTheRoot?src=hash">#FergusonTheRoot</a> <a href="https://twitter.com/hashtag/Ferguson?src=hash">#Ferguson</a></p>&mdash; Courtney Thornton (@courteroy_) <a href="https://twitter.com/courteroy_/status/537077232599330816">November 25, 2014</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">&quot;To be black and conscious in america is a constant state of rage&quot; - James Baldwin<a href="https://twitter.com/hashtag/noblackjusticenoblackfriday?src=hash">#noblackjusticenoblackfriday</a><a href="https://twitter.com/hashtag/Ferguson?src=hash">#Ferguson</a></p>&mdash; Gbenga Akinnagbe (@GbengaAkinnagbe) <a href="https://twitter.com/GbengaAkinnagbe/status/537130288787517442">November 25, 2014</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

There’s a temptation to dismiss these misquotations as characteristic of the worst follies of Internet culture, evidence of how easily lies and inaccuracies can spread throughout social media networks, proof of sloppy, irresponsible, and perhaps even sub-literary desecration—“bad readers,” as my colleague Meredith Kelling might say. The recent election cycle has indeed made it clear that social media networks and algorithms are guilty of many of these things, and they often act as echo chambers for preconceived beliefs that cordon off ideological communities of like-minded people and get further and further away from facts. But it is precisely for this reason that I believe studying these misquotations and, more broadly, studying the way that Internet communities make meaning and narratives is so urgently important.

Where these misquotations diverge from Baldwin’s actual words, they reveal some of the key tenets, values, and affects of the movement, as they reveal both what these readers _hear_ Baldwin saying and what they _want_ or _need_ him to say, making this space a site of both interpretation and authorship in its own right. For, as we’ve established, if James Baldwin didn’t speak these words, who did? Whose voice is it? Where is it coming from? I believe that Glaude was too quick to dismiss Baldwin’s appeal “as an avatar of supposed seriousness,” and I argue that Twitter users engage in collective acts of authorship under the auspices of Baldwin as a single literary avatar, creating a communal literary mythology based on Baldwin’s real life and words but also extending beyond him. I call these changes, omissions, and manipulations of Baldwin’s words “re-authorship” as opposed to “misquotation,” in order to emphasize the generative creative process at work here as opposed to insinuating only error and inaccuracy.

This quote and its many “re-authorships” reveal what the #BlackLivesMatter movement values about Baldwin and the different, sometimes competing ways that Baldwin is being used politically (for of course the #BlackLivesMatter movement is not a monolithic one).

<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">Baldwin. Rage. <a href="http://t.co/CsBuw2Xhws">pic.twitter.com/CsBuw2Xhws</a></p>&mdash; deray mckesson (@deray) <a href="https://twitter.com/deray/status/585663284138901504">April 8, 2015</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">Baldwin. Rage. (via <a href="https://twitter.com/JIJennings">@JIJennings</a>) <a href="http://t.co/QUvrjrJC32">pic.twitter.com/QUvrjrJC32</a></p>&mdash; deray mckesson (@deray) <a href="https://twitter.com/deray/status/611853727943671808">June 19, 2015</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

First, these “re-authorships” reveal an appreciation for Baldwin’s relevance and perceived prescience, that he seems like he’s clairvoyantly speaking to our contemporary moment. The most popular, “re-authored” versions of this quote update Baldwin’s language to match contemporary racial discourse and thus enhance Baldwin’s perceived prescience to the point of its erasure, collapsing the historical distance between Baldwin and the present moment. By replacing “To be a Negro” with “To be Black,” these Twitter users ditch an antiquated word that would otherwise un-hiply announce Baldwin’s historical distance and discord. They transform him from a past prophet into a present living ally and member of the movement, who speaks in the contemporary moment in the language of the contemporary moment. 

Second, these readers champion Baldwin’s intellectuality and systemic understanding of history and identity, even while they dispense with some of the characteristic prose style that allowed Baldwin to complexly explore and elucidate these subjects during his career—his penchant for careful qualifiers, multiple clauses, and general long-windedness. These Twitter users extract what they take to be the essential conceptual nuggets and craft them into a more concise and confident, 140-character abiding style. Baldwin’s second infinitive and qualifier—“to be a Negro and _to be relatively conscious_”—gets lopped off and transformed into a single compact identity—“to be Black and conscious.” This powerful, rearranged phrase echoes one of the #BlackLivesMatter movement’s persistent calls, to “stay woke,” a slang phrase that means to be “awake” or “conscious” of systemic racism and injustice, a phrase that gained traction on Black Twitter and has been strongly taken up as a rallying cry of the #BlackLivesMatter movement especially since Ferguson. These Twitter re-authorships thus make Baldwin into a sort of literary antecedent of “wokeness.” The explicit naming of “America” also demonstrates an appreciation for Baldwin’s understanding of the particularities of American history, which they enhance by naming it and pinning it down. 

Third, and perhaps most important, these readers clearly invoke Baldwin’s rage. Tellingly, what remains the same throughout every single evolution of this quote is the word rage. This is not loving Baldwin, who we see invoked elsewhere in the archive:

<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">&quot;This fight begins in the heart&quot;: <a href="https://twitter.com/LailaLalami">@LailaLalami</a> on reading James Baldwin as Ferguson seethes: <a href="http://t.co/pwErhUga3Z">http://t.co/pwErhUga3Z</a></p>&mdash; NPR Books (@nprbooks) <a href="https://twitter.com/nprbooks/status/501866250973478912">August 19, 2014</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">Love takes off the masks that we fear we cannot live without and know we cannot live within. + <a href="https://twitter.com/hashtag/jamesbaldwin?src=hash">#jamesbaldwin</a> <a href="https://twitter.com/hashtag/NMOS14?src=hash">#NMOS14</a> <a href="https://twitter.com/hashtag/Ferguson?src=hash">#Ferguson</a></p>&mdash; Mihee Kim-Kort (@miheekimkort) <a href="https://twitter.com/miheekimkort/status/500618364524691456">August 16, 2014</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">Bill T. Jones <a href="https://twitter.com/NewYorkLiveArts">@NewYorkLiveArts</a>: James Baldwin loved America. He just wanted it to make good on its promises <a href="https://twitter.com/hashtag/Ferguson?src=hash">#Ferguson</a> <a href="http://t.co/MVMmMOSeNC">http://t.co/MVMmMOSeNC</a></p>&mdash; CBCSundayEdition (@CBCSunday) <a href="https://twitter.com/CBCSunday/status/538880647930994688">November 30, 2014</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

This is angry Baldwin. By manipulating the sentence’s conclusion from the more open-ended and cautious “in a rage almost all the time” to the more permanent, climactic “constant state of rage,” these readers place special emphasis on “rage.” And this is where I think Baldwin’s literary and intellectual mythos most comes into play, the reason Twitter users respond to this quote in particular and why they retain his attribution even when they change his words. 

Because the collective outrage over Michael Brown’s shooting and Darren Wilson’s non-indictment---and the protests happening in the streets across the country---was being dismissed and criminalized as "rioting" and "thuggish," as unwarranted and overblown. These Twitter users are thus historicizing, legitimizing, and giving license to their own rage by invoking it through Baldwin, an eloquent, elite artist recognized by the establishment. This is not the anger of rioting thugs; this is the anger of an articulate, textually-deft, and conscious movement. One Twitter user expressed frustration about the movement's gravitation toward James Baldwin as model and muse, pointing out the potential dissonance between the language and experiences of James Baldwin and that of everyday black teenagers in Ferguson:

[Tweet deleted]

But this tweet reveals that that’s precisely why Baldwin is being invoked and mythologized, as a pronouncement that this movement cannot be reduced only to felons with bad credit, as a way of pulling Baldwin closer to West Florissant. In short, I believe these tweets represent a complex, collective reader response, an affiliation that is being built through and around an established literary figure. Perhaps most crucially, this literary network is _not_ happening in a university classroom or at an academic conference, but rather it's happening organically on Twitter, and I think literary scholars should be paying attention.

<b>

___

<b>

[^1]: Lev Manovich, [“The Science of Culture? Social Computing, Digital Humanities and Cultural Analytics”](http://culturalanalytics.org/2016/05/the-science-of-culture-social-computing-digital-humanities-and-cultural-analytics/)

[^2]: These [openly available archives](https://archive.org/details/ferguson-tweet-ids) were collected by Ed Summers, Molly Loyd, Gregory Coleman, Kimberly Lamke, and Benjamin Sugar, and this project is indebted to their foresight in collecting these tweets and their intellectual generosity in sharing them. Twitter’s Terms of Service does not allow bulk distribution of Twitter data, but it does allow the distribution of tweet “ids,” unique identifiers assigned to every tweet which can be used to retroactively access the full tweet metadata from the Twitter API using a tool like twarc, which was also created by Ed Summers. This process is called “hydrating.” Because “hydrating” these tweets comes after the fact, however, any tweet that has been deleted between the time of its original publication and the time of hydration disappears entirely. From the 13,480,000 ids in the first collection, I was able to “hydrate” 10,441,785 tweets, a process that took approximately 8 days (since the Twitter’s API rate limit only allows requests for up to 72,000 tweets per hour). From the 15,080,078 ids in the second collection, I was able to “hydrate” 7,868,540 tweets, which reveals a surprising number of missing/deleted tweets that I would like to more fully theorize and speculate about in the future.

[^3]: For more on how I used twarc and hydration, see ["Part 1: Building the 'Tweets of a Native Son' Archive (twarc and twarc-report)"](http://melaniewalsh.org/2016/11/05/building-tweets-of-a-native-son-part1.html)

[^4]: For more on how I reshaped the JSON  data, see ["Part 2: Building the 'Tweets of a Native Son' Archive (jq and regular expressions)"](http://melaniewalsh.org/2016/11/07/building-tweets-of-a-native-son-part2.html)
