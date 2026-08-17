---
title: What a Timestamp Actually Proves
---

The whole defence of this project is one sentence. Predictions were committed to git before the scoring existed, so anybody who does not trust me can check the order for themselves.

Good. Check it.

## The gaps

Every round's pre-registration commit, against the commit that first introduces the script which produced its numbers. Read off the repository on 17 August.

| round | pre-registration | scorer first appears | gap |
|---|---|---|---|
| 3 | 22 Jul 00:55 | `nulltest.py`, 03:22 | 2h 27m |
| 4 | 11 Aug 02:07 | `score_dissent.py`, 02:17 | **10 min** |
| 6 | 14 Aug 17:26 | `score6.py`, 17:45 | 19 min |
| 7 | 14 Aug 18:27 | `score7.py`, 18:32 | **5 min** |
| 8 | 14 Aug 18:34 | `score8.py`, 18:39 | **5 min** |
| 9 | 15 Aug 16:07 | `score9.py`, 16:10 | **3 min** |
| 10 | 16 Aug 03:34 | `score10.py`, 03:40 | **6 min** |

Median gap: **six minutes.**

<svg viewBox="0 0 760 232" width="100%" style="max-width:760px;height:auto;display:block;margin:2rem auto" role="img" aria-label="Each round's gap between committing the prediction and committing the scorer. Every gap but one is a handful of minutes, so the two dots are nearly on top of each other. The median is six minutes.">
<defs><marker id="a81" markerWidth="9" markerHeight="9" refX="8" refY="3" orient="auto"><path d="M0,0 L8,3 L0,6 z" fill="currentColor"/></marker></defs>
<text x="104" y="48" fill="currentColor" font-size="12.5" text-anchor="end" font-family="inherit">round 3</text><line x1="120" y1="44" x2="620" y2="44" stroke="currentColor" stroke-width="1.6"/><circle cx="120" cy="44" r="4.5" fill="currentColor"/><circle cx="620" cy="44" r="4.5" fill="none" stroke="currentColor" stroke-width="1.8"/><text x="634" y="48" fill="currentColor" font-size="12" font-family="inherit" opacity="0.8">2h 27m</text><text x="104" y="72" fill="currentColor" font-size="12.5" text-anchor="end" font-family="inherit">round 4</text><line x1="120" y1="68" x2="154" y2="68" stroke="currentColor" stroke-width="1.6"/><circle cx="120" cy="68" r="4.5" fill="currentColor"/><circle cx="154" cy="68" r="4.5" fill="none" stroke="currentColor" stroke-width="1.8"/><text x="168" y="72" fill="currentColor" font-size="12" font-family="inherit" opacity="0.8">10 min</text><text x="104" y="96" fill="currentColor" font-size="12.5" text-anchor="end" font-family="inherit">round 6</text><line x1="120" y1="92" x2="185" y2="92" stroke="currentColor" stroke-width="1.6"/><circle cx="120" cy="92" r="4.5" fill="currentColor"/><circle cx="185" cy="92" r="4.5" fill="none" stroke="currentColor" stroke-width="1.8"/><text x="199" y="96" fill="currentColor" font-size="12" font-family="inherit" opacity="0.8">19 min</text><text x="104" y="120" fill="currentColor" font-size="12.5" text-anchor="end" font-family="inherit">round 7</text><line x1="120" y1="116" x2="137" y2="116" stroke="currentColor" stroke-width="1.6"/><circle cx="120" cy="116" r="4.5" fill="currentColor"/><circle cx="137" cy="116" r="4.5" fill="none" stroke="currentColor" stroke-width="1.8"/><text x="151" y="120" fill="currentColor" font-size="12" font-family="inherit" opacity="0.8">5 min</text><text x="104" y="144" fill="currentColor" font-size="12.5" text-anchor="end" font-family="inherit">round 8</text><line x1="120" y1="140" x2="137" y2="140" stroke="currentColor" stroke-width="1.6"/><circle cx="120" cy="140" r="4.5" fill="currentColor"/><circle cx="137" cy="140" r="4.5" fill="none" stroke="currentColor" stroke-width="1.8"/><text x="151" y="144" fill="currentColor" font-size="12" font-family="inherit" opacity="0.8">5 min</text><text x="104" y="168" fill="currentColor" font-size="12.5" text-anchor="end" font-family="inherit">round 9</text><line x1="120" y1="164" x2="130" y2="164" stroke="currentColor" stroke-width="1.6"/><circle cx="120" cy="164" r="4.5" fill="currentColor"/><circle cx="130" cy="164" r="4.5" fill="none" stroke="currentColor" stroke-width="1.8"/><text x="144" y="168" fill="currentColor" font-size="12" font-family="inherit" opacity="0.8">3 min</text><text x="104" y="192" fill="currentColor" font-size="12.5" text-anchor="end" font-family="inherit">round 10</text><line x1="120" y1="188" x2="140" y2="188" stroke="currentColor" stroke-width="1.6"/><circle cx="120" cy="188" r="4.5" fill="currentColor"/><circle cx="140" cy="188" r="4.5" fill="none" stroke="currentColor" stroke-width="1.8"/><text x="154" y="192" fill="currentColor" font-size="12" font-family="inherit" opacity="0.8">6 min</text><g fill="currentColor" font-size="12" font-family="inherit" opacity="0.75">
  <text x="120" y="30">prediction committed</text>
 </g>
 <text x="380" y="212" fill="currentColor" font-size="12.5" text-anchor="middle" font-family="inherit" opacity="0.85">median gap: <tspan font-weight="600">six minutes</tspan>. nobody gets talked out of anything in six minutes.</text>
</svg>
So if you came here expecting the timestamps to do heavy lifting, stop. Six minutes is not a period during which anybody gets talked out of anything.

And say the sharper version, because it is the one that actually bites.

> **A git timestamp proves the ordering of commits. It does not prove the ordering of thought.**

Nothing prevents somebody running the analysis in a session, seeing the answer, writing a prediction that matches it, committing that, then committing the scorer six minutes later.

Every timestamp would look exactly as it looks above. The commit graph is honest. It is measuring the wrong thing.

## The defence that does work

There is real protection here. It is not in the clock, it is in the **manifest**, and it is stronger than the thing everybody points at.

Look at what is inside a pre-registration commit.

```
4d9f8cf  PRE-REGISTRATION 6: the phrase-aware null and a translation control
         PREREGISTRATION-6.md | 186 +++++
         1 file changed
```

One file. Same for rounds 7, 8, 9 and 10. Round 9's commit message even says so out loud, *committed before score9.py exists*, which is a claim anybody can falsify in one command.

Then the scorer arrives later, in the results commit, as a brand new file.

> **The program that produced the number did not exist when the prediction was frozen.** That is not a claim about my character. It is a property of the file tree, and it survives distrusting me completely.

That defence is much harder to fake than a timestamp.

To fake it you would have to write the scorer, run it, delete it, commit the prediction, then re-create the file from scratch and commit it as new. Possible. But that is a deliberate forgery rather than a lapse, and the distance between those two is most of what any of this is for.

<svg viewBox="0 0 760 240" width="100%" style="max-width:760px;height:auto;display:block;margin:2rem auto" role="img" aria-label="Two commits side by side. The pre-registration commit holds exactly one markdown file. The results commit holds the scorer, the results and the CSV, all marked as new files, so the program did not exist when the prediction was frozen.">
<defs><marker id="a82" markerWidth="9" markerHeight="9" refX="8" refY="3" orient="auto"><path d="M0,0 L8,3 L0,6 z" fill="currentColor"/></marker></defs>
<rect x="20" y="42" width="300" height="150" rx="3" fill="none" stroke="currentColor" stroke-width="1.6"/><text x="170" y="30" fill="currentColor" font-size="12.5" text-anchor="middle" font-family="inherit" font-weight="600">the pre-registration commit</text><text x="40" y="70" fill="currentColor" font-size="12.5" font-family="inherit">PREREGISTRATION-8.md</text><rect x="440" y="42" width="300" height="150" rx="3" fill="none" stroke="currentColor" stroke-width="1.6"/><text x="590" y="30" fill="currentColor" font-size="12.5" text-anchor="middle" font-family="inherit" font-weight="600">the results commit, 5 minutes later</text><text x="460" y="70" fill="currentColor" font-size="12.5" font-family="inherit">score8.py</text><text x="722" y="70" fill="#e03131" font-size="11" text-anchor="end" font-family="inherit" font-weight="600">new</text><text x="460" y="96" fill="currentColor" font-size="12.5" font-family="inherit">RESULTS-8.md</text><text x="722" y="96" fill="#e03131" font-size="11" text-anchor="end" font-family="inherit" font-weight="600">new</text><text x="460" y="122" fill="currentColor" font-size="12.5" font-family="inherit">results_round8.csv</text><text x="722" y="122" fill="#e03131" font-size="11" text-anchor="end" font-family="inherit" font-weight="600">new</text><path d="M330,117 L432,117" stroke="currentColor" stroke-width="1.6" fill="none" marker-end="url(#at82)"/><text x="380" y="216" fill="currentColor" font-size="12.5" text-anchor="middle" font-family="inherit" opacity="0.9">the scorer is <tspan font-weight="600">absent</tspan> from the left box. that is the defence, not the clock.</text><text x="380" y="234" fill="currentColor" font-size="12" text-anchor="middle" font-family="inherit" opacity="0.65">it survives distrusting me completely</text>
</svg>
## And then there is round 2

Here is the exception, and it is the worst possible one.

```
00a9556  PRE-REGISTRATION 2: lexicon v2 + predictions,
         committed before scoring corpus2
         PREREGISTRATION-2.md   | 135 +++++
         lexicon.py             | 322 +++++
         score.py               |  89 +++++
         results_corpus_v1.csv  |  20 +++
         results_corpus_v2.csv  |  20 +++
         get_corpus2.py         | 141 +++++
```

The pre-registration and the scorer and two scored CSV files, in one commit.

The commit message is defensible. Those CSVs are the *previous* corpus, and the claim is that corpus2 had not been scored yet, which may well be exactly true. But defensible is not the standard here. **Round 2 has no manifest protection at all.** The program existed. There is nothing in the file tree that rules anything out, and a reader who distrusts me has only my word.

Now the part that makes it hurt.

**Round 2 is where the project's only surviving positive p-value lives.** p = 0.0045. The one number this whole thing has to show for itself, quoted in every later round as the thing that survived.

**And its null script was never saved.** It was run inside a session and never written to disk, so the number cannot be reproduced from the repository at all. [[Four Broken Nulls One Mistake|Post 6]] describes rebuilding it as a 48-configuration grid, which identified the lost procedure but did not restore the claim.

> **The least protected round in the project and the only unreproducible number in the project are the same round.** Nobody arranged that. It is just where the shot landed.

## What pre-registration actually buys

It does not prove honesty. It cannot. Stop asking it to.

What it does is **remove a specific list of moves**, mechanically. So they stop being available to a person acting in good faith who would otherwise take them without noticing.

| the move | what removing it costs you |
|---|---|
| pick the metric after seeing which one separates the groups | you commit to MIN before knowing it collapses |
| pick the threshold after seeing the p-value | 0.05 is fixed while it can still hurt |
| add a text to the comparison group | the Diodorus page stays on disk, unused |
| run the sensitivity analysis only when it helps | round 4's two sensitivities are declared in advance and both destroy a passing prediction |
| report the falsifier only if it did not fire | seven of them fired and all seven are in the record |

Every one of those is something I would have done. Not through dishonesty. Through the ordinary process of noticing a defensible improvement at the moment it happens to help.

That is the whole content of [[The Sample Is Part of the Claim|post 5]]'s Diodorus page. A real page, missed by a genuine bug, whose inclusion would flip a failed prediction to passing, found while fixing something else. Every step defensible. None of it felt like cheating.

Borden's diary in *The Prestige* is the shape of the good version. A true, dated, contemporaneous record, written in the knowledge that somebody hostile will one day read it. That knowledge changes what gets written, and it is the only reason the record is worth anything.

## Three rules that cost something

A rule that never costs you anything is not a rule, it is a preference. These three each took something away, which is the only reason they are worth writing down.

**The guard is symmetric.**

In the contradiction study there is a rule blocking the apologist from inventing a harmonisation the text does not supply. Obvious, and everybody who reads that study expects it.

The same rule blocks **me** from dissolving an allegation because it feels fine. Both moves are the same move. Both supply from outside what the text does not supply, and a guard pointed in one direction only is not a guard, it is a position.

That rule is why a study designed to test a hostile docket ends up reporting that 33% of the docket survives rather than 5%.

**Corrections go against the story.**

The Judas item was scored at cost 4, the maximum, meaning no rescue exists. On review it was revised down to cost 3, because an ad hoc rescue does exist even though it is bad.

That revision runs against the rhetorically stronger position. Cost 4 is the number you want if you are trying to make a point. And the Bayes calculation that consumes these numbers gained its cost-3 case **before the revised number was fed into it**, so the correction could not be tuned by watching what it did.

The scale outranks the instinct. The instinct outranks nothing.

**Report the failure at the top.**

Not in a limitations section. Not in a paragraph after the good news. Every results file in this project opens with what fired, and the surviving claim comes after.

The reason is mechanical rather than moral. A failure disclosed at the bottom is a failure the writer has already had a page to frame. Putting it first means the frame has to be built **around** it, and a frame built around a failure is a different document from a frame with a failure appended.

> **Every one of these rules is a thing I would not have done by instinct.** That is the test of whether a rule is doing work. If following it never feels like a loss, it is describing what you were going to do anyway.

## What it cannot do, demonstrated

Here is the limit, and [[Four Broken Nulls One Mistake|post 6]] is the demonstration.

**All four broken null tests happened inside pre-registered rounds.** Every one had a frozen prediction, a fixed threshold, a declared falsifier, and a commit that beat the scorer into existence. The apparatus worked exactly as designed.

And the apparatus was pointed at the hypothesis. The control test sat outside it, in the part of the work everybody trusts. It was broken in four consecutive rounds while the machinery around it ran perfectly.

> **Pre-registration protects you from choosing. It does not protect you from not noticing.** Those are different failures and only one of them has a procedure.

## What would actually be better

Since this post has spent most of its length taking the apparatus apart, it owes an answer.

**Publish the scorer's hash inside the pre-registration.** Not the scorer. Its hash, of a file that does not exist yet, is impossible. So invert it: publish the hash of the **prediction** somewhere outside your own control, before the analysis. A public commit to a repository you do not own, a timestamped post, anything with a custodian who is not you. That converts *trust my clock* into *check somebody else's*.

**Or hand the scoring to a person who has not seen the prediction.** This project has one coder and says so out loud, which is the correct disclosure and not a fix. A study with a single coder is a strong pilot. It is not a confirmation, and calling it one is the thing the whole discipline exists to prevent.

**Or, cheapest and most effective, write the falsifier into the code rather than the prose.** A prediction in a markdown file is a promise. A prediction in the scorer, which prints PASS or FAIL on its own and refuses to be talked to, is a machine.

That last one is the one this project half did, and [[A Check That Cannot Fail Prints Reassurance|post 10]] is what happened to the half.

> **None of these makes the work honest. They make specific dishonest moves expensive**, and that is all any procedure has ever done.

The version of this that does not work, and it is worth naming because it is the popular one, is adding more description of your own carefulness. A methods section is not a control. It is a claim about a control, written by the person who would have to have noticed.

## The receipt

The strongest evidence in this project that the lexicon was not tuned is not the timestamps and not the manifest. It is [[Turning Four Sentences Into Code|post 4]]'s deletions, and one further thing about them.

**Nine of the 66 lexicon words fire zero times in the entire corpus.**

A word list written after looking at the texts would contain no dead words at all. Every entry would have been justified by something it caught. Nine words that catch nothing are nine bets that lost. They are still in the file.

> **The failures are the receipt.** They prove the list was written blind, and they prove it better than any timestamp can.
>>
> A timestamp records when a file was saved. A dead word records what somebody expected before they knew.

[[Ten Rounds and the Half That Never Carried Anything|Post 9]] is what ten rounds of this produced.
