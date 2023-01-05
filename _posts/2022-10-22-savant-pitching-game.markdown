---
layout: post
title: "A Nine Inning Saga: Baseball Savant's Pitch Type Guessing Game"
categories: baseball
---

# 1
To the nonexistent readers of this blog, let me begin by apologizing for the dearth of activity these past three months. I’ve had to move cities, settle into a new apartment, and begin a new, terribly uninspiring job. But that’s a topic for another day.[^1] We’re here today to discuss baseball, or more precisely, an online game derived from the game of baseball. And some data science, too. And perhaps a congeries of other random things. This is a post that has idled on the assembly line for over two and a half months, so it’s about time I present the finished product. Let's begin.

On an ordinary mid-July evening, I was lifelessly snooping around [Baseball Savant](baseballsavant.mlb.com) after a relatively anemic performance by my beloved Cleveland Guardians: for the second night in a row, they had failed to score a single earned run against the pathetically mediocre Chicago White Sox.[^2] Then came the epochal event. Hovering my cursor over the 3x3 grid of tiny black squares at the top right corner of the page, a menu popped up, and my gaze instantly fixed on the seductive “Savant Games” link. As I moved to click it, my mind raked up old memories of high-school me playing the notoriously difficult [Winnie the Pooh’s Home Run Derby](https://www.disney--games.com/winnie_the_pooh_s_home_run_derby_338.html).[^3] Looking back now, this flash of remembrance was a most befitting portent of what was to come. I launched the first game on the list, the seemingly innocuous Pitch Type Guessing Game. Little did I know, this wily, infernal PTGG would induce levels of rage and vexation that can only be matched by watching the Cleveland Browns inventing new ways to snatch defeat from the jaws of victory. 

# 2
Here’s a screenshot of the game. It’s quite simple: 
<figure>
<img src="/assets/img/posts/PTGG.png" alt="PTGG"
class=callout>
<figcaption>If you're wondering, this was a changeup.</figcaption>
</figure>
On the left there’s a pitch gif (say this ten times fast) that will keep looping itself into eternity until a guess is entered; there’s no timer or anything. On the right are the seven choices. Apologies to eephus fans in advance. The game shows twenty pitches total, and your score is just the number, or percentage, of pitches you correctly identify.

If you have a few hours to kill, you can play the game at this [link](https://baseballsavant.mlb.com/games/pitch-type-guess). Disclaimer: if you’re a binge-watching, achievement-grabbing neurotic like myself, proceed at your own risk. Oh yeah, throughout this post I may or may not abbreviate some pitch types with their two letter shorthand, so here’s a [dictionary](https://www.mlb.com/glossary/pitch-types) just in case.

# 3
I’ll be honest—before I discovered this game I mainly just thought of pitches as fastballs, sliders, and curveballs. I knew that sinkers, cutters, and splitters existed, but I never felt the need to look into their peculiarities as they all just looked fastball-esque to me. I didn’t have the foresight to jot down my score the first time I played the game, but if I had to guess it lied somewhere around 35%.

Having failed the practice test, I tossed some searches into Google and rummaged through a potpourri of videos, articles, blogs, and random websites run by random high school baseball coaches (which were honestly quite helpful) to hone my pitch discernment skills. Here’s a well-made [video](https://www.youtube.com/watch?v=1FTFWzcgjHE) on YouTube that I found pretty useful.  And for the sake of completeness, here’s a nice [blog post](https://lokeshdhakar.com/baseball-pitches-illustrated/) I stumbled upon that depicts roughly what things look like from the catcher’s point of view.[^4]

In the middle of this learning process, something amusingly ironic occurred: what was unbelievably useless and in fact actively detrimental was the MLB website’s [“Identifying pitch types: A fan’s guide.”](https://www.mlb.com/news/identifying-pitch-types-a-fan-s-guide) Scroll down to the “Cutter” heading, and there’s a video of “Dodgers closer Kenley Jansen throwing a nasty one for a game-ending strikeout.” I literally watched the video like ten times, trying to cope with the ball’s vertical-diagonal break more characteristic of a slider. Then I realized that there was no Dodger in the video, the pitcher was not Kenley Jansen, and we were not at the end of the game. We were in the heart of the game. The pitcher was Jon Gray, and the video was from his tenure on the Rockies. Jon Gray doesn’t even throw a cutter. That pitch was a slider.

Scrolling through the rest of the article with an eye alert for trouble, I discovered that roughly half of the clips had literally nothing to do with their so-called descriptions. Perhaps a change in the backend caused the video IDs to get all scrambled up or something—who knows. What I do know is that readers who are not fully focused may leave the page more confused than they entered it. But I digress.

# 4
I want to take a brief moment to showcase two pitch gifs that are emblematic of how infuriating the PTGG can be. Due to how the videos are loaded or something the one’s shown below are slightly longer than the loop you’d see in the actual game, but whatever.[^6]

Here’s the first:
<figure>
<video controls preload="none" playsinline>
<source src="/assets/img/posts/CutawayFastball.webm" type="video/webm">
<source src="/assets/img/posts/CutawayFastball.mp4" type="video/mp4">
Your browser does not support the video tag.
</video>
<figcaption>Bases loaded down 14 in the 5th inning, nice.</figcaption>
</figure>
Honestly, this wasn’t Savant’s fault, it was the fault of the
broadcasters. Guess they really wanted that replay. But really the only
option here was to go off speed, so I guessed some type of fastball and
was too absentminded to record whether or not I was right. When I’d be
on a guessing streak and a clip like this popped up, I’d get really
sad.

And the other:
<figure>
<video controls preload="none" playsinline>
<source src="/assets/img/posts/Sidearm.webm" type="video/webm">
<source src="/assets/img/posts/Sidearm.mp4" type="video/mp4">
Your browser does not support the video tag.
</video>
<figcaption>The COVID season, what a time.</figcaption>
</figure>
So we have a sidewinder here, and I have no idea how to read them.
Based on release point most of their pitches barely have any vertical
break at all (at least on the broadcast), so I’d usually just throw out
a wild guess based on speed. In this case, it was 81 mph, and I saw the
ball drop a little bit, so I vacillated between slider and curveball
and ultimately pulled the trigger on slider. It was a fastball. I don’t
have proof, but I’m not lying. It was classified as a fastball, and
that really made me question everything I knew about the
world.[^5]

# 5
For about two days, I sat lifeless, slouched in my chair, guessing at pitch types over and over and over again. Sinker, slider, and sinker again. Every once in a while I’d record my stats, which yielded just over eighteen games of data when it was all said and done.

Before I disclose my mediocre results, let me mention that an encyclopedic knowledge of exactly what pitches every pitcher throws, what range of speeds they throw it at, and so on, would have been a massive boon to me. I did not (and still do not) possess such knowledge off the top of my head, and the chivalric part of my soul felt that I would besmirch my honor if I pulled up each pitcher’s Savant profile before guessing. With that being said, here are my percentages:

<figure>
<img src="/assets/img/posts/PTGG_Percentages.png" alt="PTGG Percentages"
class=callout>
<figcaption>Yes, this is a prebuilt theme from Excel.</figcaption>
</figure>

It doesn’t look like I improved at all over the course of the experiment, which, if my memory doesn’t fail me, is congruent with how I felt during those two days. Though to be fair to myself, I did achieve results of 90% and 95% a few times–it just so happened that I didn’t record them.[^7] 

Let’s check my platoon splits. I batted .600 against lefties and .637 against righties, which honestly surprised me quite a bit. The oblique camera angle typical of baseball broadcasts made it much easier to identify movement from right-handed pitchers. In many cases I could never distinguish between a four-seamer and a sinker when it came a southpaw, as it was basically impossible to see how much run a pitch had relative to its release point.

Here's an example. T.J. McFarland, leftie, pitching for the Athletics in 2020:
<figure>
<video controls preload="none" playsinline>
<source src="/assets/img/posts/McFarland.webm" type="video/webm">
<source src="/assets/img/posts/McFarland.mp4" type="video/mp4">
Your browser does not support the video tag.
</video>
<figcaption>For some reason I recorded this using QuickTime instead of downloading the video like I usually did.</figcaption>
</figure>
At first glance, the trajectory looks slider-like. But it’s simply too fast, and I’ve never heard of McFarland, so if I have to guess he’s probably no Gerrit Cole or Emmanuel Clasé. So it’s either a four-seamer or a sinker. Which one is it? I literally have no idea. Maybe you guess sinker because it sinks, but every ball sinks on its way to the plate. Maybe you can look at the color of the ball to determine the spin, or something. I guessed sinker, it happened to be a sinker, but I was far from confident in my choice.

# 6.
The pairs of pitches I was most likely to confuse for each other were FF & SI and SL & CU. Apropos of the first pair, there are some cases where it’s quite easy to identify a sinker. For example, take the following pitch by Jonathan Hernandez:

There’s that unmistakable torsion in its movement that will basically never exist for a four-seamer. Other times though, depending on the whims of the camera angle, I found it borderline impossible to distinguish between the two fastballs.

I’d say I’m noticeably better at maneuvering the SL & CU mix-up. In fact, to get an impression of my classification skills, we can form the confusion matrices for FF & SI and SL & CU.[^8] 

<figure>
<img src="/assets/img/posts/Confusion.png" alt="Confusion matrices"
class=callout>
<figcaption>Couldn't quite figure out how to format the table in markdown.</figcaption>
</figure>

Honestly not that great. If the gamed showed sinker, I’d guess four-seamer about 45% of the time. Perhaps I’m relying too much on the twisting motion of the baseball to identify sinkers, when in reality many of them may only exhibit a far more muted version of it. For real curveballs I’d be wrong almost 30% of the time, which isn’t that great either. If I had to guess this is probably a product of how my mental image of a “mean curve” is Clayton Kershaw’s, and his curveball has had consistently more vertical break than the average. At least I had good and acceptable performances for the four-seamer and slider respectively, which I’ll take as a win.

# 7
After a day of spamming the game over and over again, I nurtured a dubious hunch that ultimately grew into a full-on suspicion: there was simply no chance the distribution of pitches I encountered in the PTGG tallied with the true distribution of pitches in the MLB. I felt that at the very least there was an overabundance of sinkers and an insufficiency of cutters. And maybe an undersupply of changeups as well.

My hypothesis was backed up by the data. Using statistics gleaned from [Pitcher List](https://www.pitcherlist.com), we can calculate the distribution of pitch types from this season.[^9]  Here’s the table, labeled with that two-letter shorthand I alluded to earlier:

<figure>
<img src="/assets/img/posts/PitchList.png" alt="Confusion matrices"
class=callout>
<figcaption>That's actually way more pitches than I expected.</figcaption>
</figure>

The “UN” label stands for “Unknown.” Given that they make up a meager 0.05% of all pitches thrown, for the sake of simplicity (and at the expense of statistical integrity) I’m going to continue my analysis pretending they don’t exist, as the PTGG is never gonna hit me with one of them. But I would be curious to see a video of one of these pitches—are they made up of wild, feral pitches, strange grips, or something else?

So splitters are diamonds, sinkers are gold, curveballs and changeups are silver, cutters and sliders are bronze, and the old reliable four-seam fastball is iron or some other abundant metal. Looking at this data, I can tell you right off the bat[^10] that the pitches thrown in the PTGG do not reflect these percentages at all. Here’s the distribution I got from the approximately 18 games that I took notes for:

<figure>
<img src="/assets/img/posts/PTGGDist.png" alt="Confusion matrices"
class=callout>
<figcaption>The fact that I didn't get a single splitter is pretty
impressive.</figcaption>
</figure>

These two distributions are worlds part and the specifics of how they differ are pretty much in line with what my intuition told me.[^11] We can run a basic [chi-squared test](https://en.wikipedia.org/wiki/Chi-squared_test) to quantify this gap. The resulting p-value is 5.18 * 10e-35. That’s a lot of significance.

Now we can observe the nefarious PTGG designers at work. We already talked about how the hardest pitch I had trouble identifying correctly was the sinker: out of 76 sinkers seen, I mistakenly classified a whopping 34 of them as four-seam fastballs. And looking at the data, it seems like the PTGG has more than tripled the number of sinkers at the expense of savagely slashing the number of cutters, which are certainly easier to identify, given their usual slower speed and slight glove-side movement. Was this game purposely designed to make my life more miserable? I have no idea, but honestly this is as compelling evidence as there can be.

# 8
The fanatical, egotistical, and megalomaniacal parts of my brain (all three parts, in other words) could not endure the humiliation of still getting Bs and Cs and Fs on this exam despite retaking it at least a hundred times. “What if it’s Savant’s classification that’s wrong?,” I bargained.[^12] Such thoughts goaded me into looking up how Savant even determines what these pitches are in the first place.

One of the first articles I stumbled upon was this [post](https://technology.mlblogs.com/mlb-pitch-classification-64a1e32ee079) from the MLB Technology Blog, which contained everything I wanted and then some. The innards of pitch classification are exactly what you’d expect. Lots and lots of data. Unsupervised learning. A neural network named PitchNet. Now, I’m not going to profess knowledge of whatever XGBoost is, but I think there are some things worth considering.

At a high level, there’s a dangerous pitfall that all machine learning algorithms must skirt in some way, and that’s the fact that they may be unwittingly eating their own tail. More precisely, the output of the algorithm may be influencing the environment it operates in, which influences its inputs (the training data), which in turn influences its output, which in turn … you get the idea. If this self-perpetuating cycle is left to spin around on its own, there may be perverse, potentially destructive outcomes, depending on the use case.

In the case of PitchNet, the question that springs to mind is the following: where does its training data come from? Theoretically it should consist of the myriad pitches thrown every night during baseball season, but those pitches are identified immediately by Statcast using … PitchNet. There must be some exogenous source of truth, and despite the aid of a clustering algorithm, what really matters is what the pitcher says:

> We classify each pitch in each pitcher’s repertoire as the pitcher himself calls it; for instance, a pitch that one pitcher calls a cutter may be called a slider by another, even if the velocity, spin, and movement of both pitches are essentially identical. Direct quotes from the pitchers themselves, as well as from pitching coaches, managers, and other on-field staff, are used to verify each pitcher’s repertoire along with images of the pitchers using different pitch grips.

So what’s a slider? Sure, it’s a breaking ball, faster than a curveball, slower than a fastball, and breaks glove-side. But at the end of the day, it seems that a slider is whatever a pitcher thinks is a slider. So now we have another reason why the PTGG can be so damn vexing.

# 9
After a couple days I came to accept my leaves-much-to-be-desired pitch classification skills. My eyes, it seemed, were simply not as keen as those of PitchNet. I resolved to vulgarize things: out with the four-seamer, two-seamer, sinker, slider, and curveball. Fastball and breaking ball were all I needed.

Well, maybe. I had one final dalliance with the old PTGG to scrape a few videos for this post, and something did happen:

<figure>
<img src="/assets/img/posts/100.png" alt="100%"
class=callout>
<figcaption>I don't remember how it happened exactly, but I probably
got 15 four-seam fastballs or something.</figcaption>
</figure>

A perfect game.


[^1]: If you’re one of my coworkers, please understand that you’re basically the only thing between me and madness.
[^2]: As I’m writing this, we just lost a tough five-game ALDS to the Yankees. We’ll be back next year.
[^3]: It’s basically impossible to beat Christopher Robin.
[^4]: I think this guy is a UI designer; his blog is really cool.
[^5]: Turns out that the pitcher is <a href="https://baseballsavant.mlb.com/savant-player/brian-moran-57238">Brian Moran</a>. He debuted in 2019, is 34 years old (probably what they’re talking about in the video), and in fact, throws an 82mph fastball. In 2020 he threw 110 pitches for a 9.26 ERA.
[^6]: If none of the videos from here on out load, I apologize. Try another browser maybe. I was running into issues with Chrome that I had no idea how to fix. Aargh.
[^7]: Don’t think I dipped below 35%, at least.
[^8]: You might protest that this analysis excludes the times when the pitch was FF and I guessed FC, for example. Two things to note: first, on fastballs I usually always guessed FF or SI, as FC rarely showed up in the game (this will be analyzed in the next section); second, SL and CU pitches usually have enough break that I would basically never guess anything else.
[^9]: Okay, I lied. I actually did this calculation in late-July, when I first broke ground on this post—so there’s only about a half season’s worth of data. You might also object that the PTGG has pitches from as early as the 2020 season; to that I agree, but as we will soon see the discrepancy is so large that I am more than confident that expanding the dataset would yield little to no change.
[^10]: Sorry.
[^11]: You may wonder if Pitcher List has a classification method distinct from that of the MLB. I seriously doubt that’s the case, as the MLB has access to exclusive data captured directly at ballparks that no third party tool could even dream of having.
[^12]: This is some variant of that Seymour Skinner meme.
