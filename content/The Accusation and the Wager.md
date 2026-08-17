---
title: The Accusation, and the Wager
---

The standard objection to René Girard is that his theory cannot lose.

Put it at full strength. The weak version is easy to knock down and I am not interested in that.

Girard says human desire is copied from other people. Copying turns models into rivals. Rival crowds discharge themselves onto a single victim, and the peace afterwards makes the victim look guilty. Myth is the surviving story, told by the people who did it, from inside. Which is why the victim in a myth is always genuinely monstrous.

Now watch what that does to evidence.

A text where the victim looks guilty confirms the theory, because that is what the mechanism produces. A text where the victim looks innocent confirms it too, because that is the mechanism being exposed. A text with no visible victim confirms it best of all, since the whole point is that the mechanism hides itself.

There is no text you could hand a Girardian that would make him say the words *this one does not fit*.

That is not a cheap shot. It is the objection his defenders have to answer.

And the honest answer is that most Girardian reading is interpretation rather than measurement. Interpretation of that kind cannot fail.

## The wager

So I made a bet with myself. Take the part of the theory that is enumerable, turn it into code, and write down what it predicts before running it.

Girard says the persecution mechanism leaves four marks in the text it produces. A social crisis. An accusation of crimes that break the deepest boundaries. Marks that single out the victim. And the collective violence itself. Four sentences, in his own books, that are specific enough to make into word lists.

So I made word lists. Then I ran them over a corpus of Greek and Roman literature that I had not read.

The discipline is one rule, and everything else in this series comes out of it.

> **Commit the prediction to git before the scorer exists. Then report what happened, including when what happened is that I was wrong.**

That rule is cheap to state and expensive to keep.

It cost me the ability to fix an instrument after seeing what it did. It cost me a corpus page that would have flipped a failed prediction to passing. I found that page while fixing an unrelated bug, and I had to exclude it. It is still on disk. Unused.

<svg viewBox="0 0 760 210" width="100%" style="max-width:760px;height:auto;display:block;margin:2rem auto" role="img" aria-label="The order of work: write the prediction, commit it, build the scorer, run it, report the result even when it fails. The arrow running backwards from run to prediction is crossed out.">
  <defs>
    <marker id="ar" markerWidth="9" markerHeight="9" refX="8" refY="3" orient="auto">
      <path d="M0,0 L8,3 L0,6 z" fill="currentColor"/>
    </marker>
  </defs>
  <g fill="none" stroke="currentColor" stroke-width="1.6">
    <rect x="8" y="46" width="132" height="42" rx="3"/>
    <rect x="164" y="46" width="132" height="42" rx="3"/>
    <rect x="320" y="46" width="132" height="42" rx="3"/>
    <rect x="476" y="46" width="132" height="42" rx="3"/>
    <rect x="632" y="46" width="120" height="42" rx="3"/>
  </g>
  <g fill="currentColor" font-size="13" text-anchor="middle" font-family="inherit">
    <text x="74" y="72">write prediction</text>
    <text x="230" y="72">commit</text>
    <text x="386" y="72">build scorer</text>
    <text x="542" y="72">run</text>
    <text x="692" y="72">report</text>
  </g>
  <g stroke="currentColor" stroke-width="1.6" marker-end="url(#ar)" fill="none">
    <path d="M140,67 L160,67"/>
    <path d="M296,67 L316,67"/>
    <path d="M452,67 L472,67"/>
    <path d="M608,67 L628,67"/>
    <path d="M692,88 L692,126"/>
  </g>
  <text x="692" y="144" fill="currentColor" font-size="12.5" text-anchor="middle" font-style="italic">even when it fails</text>
  <path d="M542,88 C542,168 74,168 74,90" fill="none" stroke="currentColor" stroke-width="1.6" stroke-dasharray="5 4" opacity="0.55" marker-end="url(#ar)"/>
  <g stroke="#e03131" stroke-width="3.4" stroke-linecap="round">
    <path d="M296,148 L324,176"/>
    <path d="M324,148 L296,176"/>
  </g>
  <text x="310" y="198" fill="#e03131" font-size="12.5" text-anchor="middle">this arrow is the whole problem</text>
</svg>

## What actually got built

Three instruments, not one, and they test different things.

**The scapegoat detector.** Four word lists over 73 Greek and Roman texts, plus the four Gospels and 23 tragedies. Ten pre-registered rounds between July and August. This is the one most of the series is about.

**The interlock instrument.** A separate study asking whether the New Testament's internal contradictions are what a hostile compiler says they are. The docket comes from atheist aggregators, so I could not skip the hard ones. Every allegation runs through nine gates and a cost scale.

**The conversion instrument.** Three of the seven transformations Girard names at the end of *Deceit, Desire and the Novel*. Scored on the last 1,500 words of novel endings.

They are separate studies with separate pre-registrations. None of them rescues another.

## What a falsifier is, since seven of them fired

A prediction says what you expect. A **falsifier** says what would make you stop.

They are not the same thing and the second one is rarer. A prediction can fail and leave the theory untouched, because you can always say the instrument was blunt. A falsifier is a number, fixed before the run, attached to a sentence of the form *if this comes out above that, the round does not get to claim what it was built to claim.*

Three examples from this project, all written before the data existed.

**If the median result across all texts is inside this band, report the round as under-powered rather than as an absence.** That one fired. The statistic came back at −0.012 and a round that would otherwise have read as *the effect is not there* was reported instead as *this instrument could not have seen it*.

**If more than 40% of rejections come through two gates, the rejection rate is unreliable.** That one fired at 67.6%, in the contradiction study, and it is the headline of that study rather than a footnote.

**If dropping one unit changes the verdict, say so.** That one fired too. Four of twenty-two units move a verdict on their own.

> **A fired falsifier is a success. It is the instrument doing the one thing an instrument is for.**

The reason to say that loudly is that the alternative is worse than it looks. A project with no falsifiers is not a project with fewer problems. It is a project where the problems have nowhere to appear.

## The tally, which is the point

As of the forensic record's count on 14 August, across 51 committed predictions and falsifiers:

| | |
|---|---|
| clean passes | **14** |
| failures | **22** |
| falsifiers fired | **7** |
| vacuous passes | **2** |
| never run | **3** |

Two more rounds ran after that count and neither improved it.

<svg viewBox="0 0 760 118" width="100%" style="max-width:760px;height:auto;display:block;margin:2rem auto" role="img" aria-label="A single bar showing 14 clean passes against 22 failures, 7 fired falsifiers, 2 vacuous passes and 3 never run. The passing segment is under a third of the bar.">
  <g stroke="currentColor" stroke-width="1.4">
    <rect x="10"  y="20" width="210" height="46" fill="currentColor" fill-opacity="0.82"/>
    <rect x="220" y="20" width="330" height="46" fill="currentColor" fill-opacity="0.13"/>
    <rect x="550" y="20" width="105" height="46" fill="currentColor" fill-opacity="0.13"/>
    <rect x="655" y="20" width="30"  height="46" fill="currentColor" fill-opacity="0.13"/>
    <rect x="685" y="20" width="45"  height="46" fill="currentColor" fill-opacity="0.13"/>
  </g>
  <g fill="currentColor" font-size="13" text-anchor="middle" font-family="inherit">
    <text x="115" y="49" font-weight="600" fill="var(--light, #fff)" style="mix-blend-mode:difference">14</text>
    <text x="385" y="49">22</text>
    <text x="602" y="49">7</text>
    <text x="707" y="49">3</text>
  </g>
  <g fill="currentColor" font-size="12.5" font-family="inherit" opacity="0.85">
    <text x="115" y="88" text-anchor="middle">clean passes</text>
    <text x="385" y="88" text-anchor="middle">failures</text>
    <text x="602" y="88" text-anchor="middle">falsifiers fired</text>
    <text x="707" y="88" text-anchor="middle">never run</text>
    <text x="670" y="106" text-anchor="middle" opacity="0.75">2 vacuous passes between them</text>
  </g>
</svg>

Twenty-two failures is not an embarrassing number to publish. It is the only number that makes the rest of the series worth reading.

A project of this shape coming back with twenty-two passes would tell you something got adjusted. And you would be right.

The repository is 51 commits across ten working days. Not months. I said months once and got corrected, and the correction was fair, so I counted.

## What I am not claiming

Fix the ceiling now, so nothing later reads as a bait and switch.

**None of this tests whether Christianity is true.** The detector compares vocabularies across texts. The interlock study asks whether a document transmits reliably, which is a question about transmission and not about miracles.

The one study that touches the resurrection has a ceiling written into its pre-registration. The best available outcome is *this case is honestly built*. Never *it happened*. Once the facts are fixed, the inference is dominated by your prior on miracles, and no source check touches a prior.

**None of it tests Girard's mimetic psychology.** The copying, and the model becoming the rival, are never tested by anything here. Only the four stereotypes are measurable, and they are the last part of the theory rather than the interesting one.

**And a lexical instrument measures vocabulary.** It cannot tell that a dissenting word belongs to a person separating from a crowd rather than to a hymn. One text in the corpus scores the maximum on the dissent lexicon because it is a prayer full of the words *blameless* and *defend*. That warning stands over every result here.

## What the rest of these posts are

Eleven of them, and this is the first. Some run longer on purpose. The ones with a real finding get room to explain it, and the connective ones do not.

| # | what it does |
|---|---|
| 2 | Girard in the minimum. Only what you need to follow the instrument |
| **3** | the decision rule Girard wrote down, which nobody in this project had read |
| 4 | turning four sentences into code, and the choice between adding up and taking the smallest |
| 5 | the corpus, and why the sample is part of the claim |
| **6** | four broken control tests and the one mistake underneath all four |
| 7 | the arithmetic, all of it, from a rate to a power calculation |
| 8 | pre-registration, and why the timestamp proves less than you think |
| **9** | ten rounds, and the half of the instrument that never carried anything |
| 10 | the checks that could not fail, including three of my own |
| 11 | the other two instruments, and what the whole thing cost |

The four in bold are where the actual findings are. If you only read four, read those.

## How to check any of this without trusting me

The series claims everything is verifiable, so here is what that means in practice. Each of these takes a few minutes and needs nothing but the repository and something you already own.

**Count `king` in one page of the *Odyssey*.** One of the four buckets is 44% a single word, and a hospitality scene consequently outscores every tragedy in the corpus. You need the text and your eyes.

**Read the commit order.** `git log` settles which files existed in which commit and when, and it settles it against me as much as for me.

**Recompute one rate.** Hits divided by words, times a thousand. A calculator. If the number in the file disagrees with the number you get, that is a finding and it is yours.

**Rerun one scorer** and check whether the output matches the committed results file. This one requires Python and about a minute.

**Open a cited verse** and see whether it says what the compiler claimed it says. Five allegations in the hostile docket misdescribe their own citations. Any Bible will do.

**Count the files in the corpus directory.** Then compare that number to the one the pre-registration says is there. They do not match, and no verdict in the project depends on it, which is exactly why nobody checked for eight rounds.

> **A claim nobody can check is a claim nobody should believe, and that includes every claim in this series.**

The reason to list these rather than assert the general principle is that the general principle is free and the list is not. Publishing a repository where the awkward things are findable costs something. Six of the eight most damaging findings in this series were found by somebody going and looking, and in every case that somebody was me, which is exactly the weakness in the arrangement.

## The one sentence the project turns on

It is worth planting here, because it is the thing I would keep if everything else in this series turned out to be wrong.

> **A check that cannot fail prints reassurance.**

I built several. Not through carelessness. Through the ordinary process of writing a control test, watching it pass, and moving on. Which is what everybody does, and which is the exact circumstance under which a broken control is invisible.

The project caught three of its own. Not by being clever. It caught them by printing the numbers next to the verdict, every time, so a verdict that disagreed with its own evidence had somewhere to be noticed.

The rest of the series follows.
