---
title: Four Broken Nulls, One Mistake
---

I measured something and got 6.10.

Is that big?

You cannot answer that. Nothing about the number tells you. 6.10 per thousand words is not large or small until something is standing next to it. The thing you build to stand next to it is called a null.

This post is about the four times I built one wrong.

Not four different mistakes. The same mistake, four times, across four rounds, over three weeks, by somebody who was writing pre-registrations and declaring falsifiers the entire time. It is the most useful thing this project produced, and it has nothing to do with Girard.

## What the thing actually is

A null is not a claim about the world. It is a machine for manufacturing fake data that resembles your real data in every respect except the one you are testing.

So building one is not a statistical act. It is a modelling act. Only two questions.

| | |
|---|---|
| **1** | what does my fake data **keep** from the real data? |
| **2** | what does it **destroy**? |

Whatever it destroys is what you are testing. Nothing else.

If it destroys two things, you are testing two things and you will not be able to say which one moved. If it destroys nothing that matters, you are testing nothing, and the test will still print a number, and the number will look like a result.

<svg viewBox="0 0 760 224" width="100%" style="max-width:760px;height:auto;display:block;margin:2rem auto" role="img" aria-label="The two questions to ask of any null: what does the fake data keep, and what does it destroy. An arrow runs from the destroys column to a label reading this, and only this, is your hypothesis.">
<defs><marker id="a61" markerWidth="9" markerHeight="9" refX="8" refY="3" orient="auto"><path d="M0,0 L8,3 L0,6 z" fill="currentColor"/></marker></defs>
<g fill="none" stroke="currentColor" stroke-width="1.6">
  <rect x="60" y="34" width="270" height="130" rx="3"/><rect x="360" y="34" width="270" height="130" rx="3"/>
 </g>
 <line x1="60" y1="68" x2="330" y2="68" stroke="currentColor" stroke-width="1.6"/>
 <line x1="360" y1="68" x2="630" y2="68" stroke="currentColor" stroke-width="1.6"/>
 <rect x="360" y="34" width="270" height="34" fill="currentColor" fill-opacity="0.12"/>
 <g fill="currentColor" font-family="inherit" text-anchor="middle">
  <text x="195" y="57" font-size="13.5" font-weight="600">what it KEEPS</text>
  <text x="495" y="57" font-size="13.5" font-weight="600">what it DESTROYS</text>
  <g font-size="12.5" opacity="0.88">
   <text x="195" y="92">every word, exactly</text><text x="195" y="114">every bucket total</text>
   <text x="195" y="136">the whole-text rate</text><text x="195" y="156">the text's length</text>
   <text x="495" y="92">the order they were in</text><text x="495" y="114">which words are near which</text>
   <text x="495" y="136">any passage, any scene</text><text x="495" y="156">any moment</text>
  </g>
 </g>
 <path d="M646,99 L692,99" stroke="#e03131" stroke-width="2" fill="none" marker-end="url(#at61)"/>
 <text x="700" y="94" fill="#e03131" font-size="12" font-family="inherit" font-weight="600">this,</text>
 <text x="700" y="110" fill="#e03131" font-size="12" font-family="inherit" font-weight="600">and only this,</text>
 <text x="700" y="126" fill="#e03131" font-size="12" font-family="inherit" font-weight="600">is your hypothesis</text>
 <text x="345" y="200" fill="currentColor" font-size="12.5" text-anchor="middle" font-family="inherit" opacity="0.85">if it destroys two things you are testing two things.</text>
 <text x="345" y="218" fill="currentColor" font-size="12.5" text-anchor="middle" font-family="inherit" opacity="0.85">if it destroys nothing that matters you are testing nothing.</text>
</svg>
## You already know one

A control group.

Same age distribution, same sex ratio, same comorbidities, same hospital, same season, same everything except the drug. Ask the two questions of it. It keeps age, sex, comorbidity, setting. It destroys exposure to the drug. So it tests the drug.

This is not an analogy for a null. It is a null. Same object, different room.

And the ways a control group goes wrong are the ways every null in my project went wrong.

Match on too much and you learn nothing. Match the control group on the drug itself and the two arms are identical. Less obviously, match on something downstream of the drug and you have controlled away the effect you came to find.

Match on too little and you are testing the wrong thing. If the control group is younger, you are testing age. The write-up will say you were testing the drug, and the write-up will not know.

That last sentence is the whole post. A badly built null does not weaken a study. It silently answers a different question, at full confidence, under the heading you wrote before you knew.

## Building one, properly, once

The question in round 3 was whether the four stereotypes converge on a single passage. Girard's claim is about an event. A text that scores high on totals has not shown you an event, it has shown you a vocabulary.

So the fake data has to be a text with everything the real text has, except that nothing is anywhere in particular.

Take the text. Put every word in a hat. Draw them out in random order.

| it keeps | it destroys |
|---|---|
| every single word, exactly | the order they were in |
| every bucket's total count, exactly | which words are near which |
| the whole-text rate, to the last decimal | any passage, any scene, any moment |
| the text's length | |

It isolates position and nothing else. And notice what falls out of that. A text can be drenched in all four stereotypes and still fail this null, because the shuffled version is drenched too. The null is immune to the density problem that wrecked the round before it.

That is not luck. That is what a well-chosen null buys.

Then one implementation detail decides everything. The lexicon contains multi-word forms. `limb from limb`, `cast out`, `with one voice`. Shuffle the raw words and every phrase dissolves. `limb from limb` becomes three words scattered across the book, and the fake text scores lower than the real one on phrases for a reason that has nothing to do with position.

The null would be testing whether phrases exist. You would report it as localization.

The fix is to mark each phrase hit at its first word and shuffle the marks rather than the words, so a phrase travels as one unit. One line. Without it the round measures the wrong thing and looks like a triumph.

Run it five hundred times per text and you have five hundred fake answers to put beside the real one.

$$ z = ( \text{observed} - \text{mean of the fakes} ) / \text{sd of the fakes} $$

z is how many typical wobbles away from nothing you are. Zero means you look exactly like nothing happening.

## Now the four

Every one of these ran correctly. None of them is a coding bug. That is the property that makes this class of error dangerous. A broken null does not crash. It reports.

<svg viewBox="0 0 760 200" width="100%" style="max-width:760px;height:auto;display:block;margin:2rem auto" role="img" aria-label="Four panels, one per broken null. In each, what the statistic depended on and what the null actually randomised are different things. The four panels are the same picture.">
<defs><marker id="a62" markerWidth="9" markerHeight="9" refX="8" refY="3" orient="auto"><path d="M0,0 L8,3 L0,6 z" fill="currentColor"/></marker></defs>
<rect x="24" y="34" width="164" height="126" rx="3" fill="none" stroke="currentColor" stroke-width="1.4"/><text x="106" y="24" fill="currentColor" font-size="12.5" text-anchor="middle" font-family="inherit" font-weight="600">round 3</text><text x="106" y="62" fill="currentColor" font-size="11.5" text-anchor="middle" font-family="inherit" opacity="0.7">statistic needs</text><text x="106" y="80" fill="currentColor" font-size="13" text-anchor="middle" font-family="inherit" font-weight="600">clumping</text><text x="106" y="112" fill="currentColor" font-size="11.5" text-anchor="middle" font-family="inherit" opacity="0.7">null randomised</text><text x="106" y="130" fill="#e03131" font-size="13" text-anchor="middle" font-family="inherit" font-weight="600">word order</text><text x="106" y="152" fill="#e03131" font-size="12.5" text-anchor="middle" font-family="inherit" font-weight="600">no match</text><rect x="208" y="34" width="164" height="126" rx="3" fill="none" stroke="currentColor" stroke-width="1.4"/><text x="290" y="24" fill="currentColor" font-size="12.5" text-anchor="middle" font-family="inherit" font-weight="600">round 4</text><text x="290" y="62" fill="currentColor" font-size="11.5" text-anchor="middle" font-family="inherit" opacity="0.7">statistic needs</text><text x="290" y="80" fill="currentColor" font-size="13" text-anchor="middle" font-family="inherit" font-weight="600">phrases</text><text x="290" y="112" fill="currentColor" font-size="11.5" text-anchor="middle" font-family="inherit" opacity="0.7">null randomised</text><text x="290" y="130" fill="#e03131" font-size="13" text-anchor="middle" font-family="inherit" font-weight="600">unigrams only</text><text x="290" y="152" fill="#e03131" font-size="12.5" text-anchor="middle" font-family="inherit" font-weight="600">no match</text><rect x="392" y="34" width="164" height="126" rx="3" fill="none" stroke="currentColor" stroke-width="1.4"/><text x="474" y="24" fill="currentColor" font-size="12.5" text-anchor="middle" font-family="inherit" font-weight="600">round 5</text><text x="474" y="62" fill="currentColor" font-size="11.5" text-anchor="middle" font-family="inherit" opacity="0.7">statistic needs</text><text x="474" y="80" fill="currentColor" font-size="13" text-anchor="middle" font-family="inherit" font-weight="600">phrase rarity</text><text x="474" y="112" fill="currentColor" font-size="11.5" text-anchor="middle" font-family="inherit" opacity="0.7">null randomised</text><text x="474" y="130" fill="#e03131" font-size="13" text-anchor="middle" font-family="inherit" font-weight="600">first tokens</text><text x="474" y="152" fill="#e03131" font-size="12.5" text-anchor="middle" font-family="inherit" font-weight="600">no match</text><rect x="576" y="34" width="164" height="126" rx="3" fill="none" stroke="currentColor" stroke-width="1.4"/><text x="658" y="24" fill="currentColor" font-size="12.5" text-anchor="middle" font-family="inherit" font-weight="600">round 7</text><text x="658" y="62" fill="currentColor" font-size="11.5" text-anchor="middle" font-family="inherit" opacity="0.7">statistic needs</text><text x="658" y="80" fill="currentColor" font-size="13" text-anchor="middle" font-family="inherit" font-weight="600">violence clustering</text><text x="658" y="112" fill="currentColor" font-size="11.5" text-anchor="middle" font-family="inherit" opacity="0.7">null randomised</text><text x="658" y="130" fill="#e03131" font-size="13" text-anchor="middle" font-family="inherit" font-weight="600">all positions</text><text x="658" y="152" fill="#e03131" font-size="12.5" text-anchor="middle" font-family="inherit" font-weight="600">no match</text><text x="380" y="190" fill="currentColor" font-size="12.5" text-anchor="middle" font-family="inherit" opacity="0.85">four rounds, four different mistakes, one shape</text>
</svg>
### Round 3, Null B, and it favoured the wrong texts by construction

Alongside the shuffle I ran a second null. Build random lexicons matched on word frequency, score those, see whether Girard's four buckets beat them.

They did not. Random word sets scored higher. On the *Bacchae*, the play Girard uses as his central example, the observed value was 2.0 against a null mean of 4.41.

That is not evidence about Girard.

The statistic was a minimum across four buckets. Random words matched on individual frequency spread out across topics, so they appear at more uniform rates, and a uniform rate raises a minimum. Any thematically coherent word set clumps. Any clumpy set loses this comparison.

Null B would fail identically for any four topical word sets, on any corpus, about anything. It tests nothing.

My error. And it was in the pre-registration, so it was frozen before anyone could notice it.

### Round 4, D4, and the effect was never in the null's way

Round 4 tested a fifth bucket for dissenting voices. The frequency-matched null came back at 591 of 2000 draws beating the observed value, p = 0.296.

Read alone that says the instrument is weak. Split the instrument in half and it says something else entirely.

| half | GOSPEL | TRAGEDY | MYTH |
|---|---|---|---|
| unigrams | 0.367 | **0.639** | 0.486 |
| phrases | **0.982** | 0.156 | 0.108 |

The unigram half runs backwards. On single words the Gospels score lowest of the three tiers, and the observed Gospel-minus-myth separation on unigrams is −0.075 per thousand. It is negative. Of course 591 random word sets beat it.

The null matched unigrams only. Fifty-three phrases sat untouched in every one of the 2000 draws, contributing their full separation to the observed value and to the null alike, cancelling out, leaving the comparison to be decided entirely by the half running the wrong way.

This is the sneakiest of the four. It did not destroy too much or too little. It operated on the wrong object.

A null that leaves the effect in place is not a weak test of your hypothesis. It is a confident test of something else.

### Round 5, and a rare phrase became a very common word

The round 2 null script was lost, so I rebuilt it as a grid of 48 configurations across five free parameters and let the grid tell me which one the original had been.

The grid did not scatter. It split, cleanly, on one parameter.

| arm | n | p range | null sd |
|---|---|---|---|
| unigrams-only | 24 | 0.00050 to 0.00700 | 2.46 to 3.58 |
| phrase-aware | 24 | 0.15892 to 0.54123 | 10.48 to 13.09 |

The phrase-aware arm inherited its procedure from round 3. It matched a multi-word form on the corpus frequency of its **first token**.

`with one voice` occurs 3 times in the corpus. `with` occurs 8,294 times. So the null replaced a phrase appearing three times with a word appearing eight thousand times, and called that frequency-matched.

Median inflation across all 68 phrases: 113 times. In aggregate the arm swapped 206 phrase-occurrences for words totalling 65,137 occurrences, a 316-fold inflation.

You can see it in the output without any argument about it. The null's standard deviation goes from about 3 to about 11 the moment the arm is switched on. A null whose spread is four times the instrument's cannot reject anything.

Third instance. And I want to name what makes round 5 worse than the two before it. Round 3's Null B was a bad idea. Round 4's D4 was a bad match. Round 5 was neither. Round 5 inherited round 3's code.

### Round 7, Null A, and every tier came out repelling

Round 7 measured how far dissent vocabulary sits from violence vocabulary, against a null that permuted token positions uniformly. Same shuffle as round 3, reused.

Mean z came out positive in every tier. Gospel +0.276, tragedy +0.665, myth +0.326. Positive means dissent sits *farther* from violence than chance would put it.

Every tier repels. That is not a Girardian result, not an anti-Girardian result, and not plausible as a fact about narrative.

Here is what happened, and it is measurable without any null at all. Uniform permutation destroys the locality of the violence hits too. And violence hits are not uniformly located.

Index of dispersion of the gaps between consecutive violence hits. It is 1.00 for a uniform scatter.

| tier | n | median dispersion |
|---|---|---|
| GOSPEL | 4 | 466.9 |
| TRAGEDY | 23 | 263.3 |
| MYTH | 61 | 350.9 |

All 88 measurable texts sit above 1.0. The median is 323. Violence vocabulary is concentrated in battle scenes, executions and lynchings, by a factor of a few hundred over uniform, which anyone who has read a poem could have told me.

So the null spread the violence evenly, which shortened the nearest-violence distance in the fake data, which pushed the observed z positive regardless of where the dissent actually sat.

The statistic was sensitive to the arrangement of the comparison set. The null destroyed that arrangement.

## The check that would have caught all four, and it takes ten seconds

| ask | round 3 | round 4 | round 5 | round 7 |
|---|---|---|---|---|
| what does my statistic depend on? | clumping | phrases | phrase rarity | violence clustering |
| what does my null randomise? | order | unigrams | first tokens | all positions |
| **do those match?** | **no** | **no** | **no** | **no** |

Four rounds. Four no's. The table is three rows long and I never filled it in.

<svg viewBox="0 0 760 196" width="100%" style="max-width:760px;height:auto;display:block;margin:2rem auto" role="img" aria-label="The three-row check drawn as a blank form to copy: what does my statistic depend on, what does my null randomise, do those match.">
<defs><marker id="a63" markerWidth="9" markerHeight="9" refX="8" refY="3" orient="auto"><path d="M0,0 L8,3 L0,6 z" fill="currentColor"/></marker></defs>
<g fill="none" stroke="currentColor" stroke-width="1.4">
  <rect x="90" y="26" width="580" height="132" rx="3"/>
  <line x1="90" y1="70" x2="670" y2="70"/><line x1="90" y1="114" x2="670" y2="114"/>
  <line x1="430" y1="26" x2="430" y2="158"/>
 </g>
 <g fill="currentColor" font-family="inherit" font-size="13">
  <text x="110" y="54">what does my statistic depend on?</text>
  <text x="110" y="98">what does my null randomise?</text>
  <text x="110" y="142" font-weight="600">do those match?</text>
 </g>
 <g stroke="currentColor" stroke-width="1.2" opacity="0.35">
  <line x1="452" y1="56" x2="648" y2="56"/><line x1="452" y1="100" x2="648" y2="100"/><line x1="452" y1="144" x2="648" y2="144"/>
 </g>
 <text x="380" y="184" fill="currentColor" font-size="12.5" text-anchor="middle" font-family="inherit" opacity="0.8">ten seconds. copy it. I never filled it in, four times.</text>
</svg>
The obvious question is why. Not why I got a null wrong once, which is ordinary. Why I got it wrong four times while running a pre-registration discipline built specifically to catch me.

The answer is that the null felt like the check rather than the thing being checked.

Every one of those rounds had a careful pre-registration protecting the prediction. Predictions were frozen, committed, timestamped, judged against thresholds fixed in advance. All of that machinery pointed at the hypothesis. The null sat outside it, in the part of the work labelled *controls*, which is the part everybody trusts.

Test a lock by pulling on the door. The door does not open. The lock goes in the log as working.

The test was real. The door was genuinely pulled. It exercised a property the lock does not fail on, and the result was filed as reassurance, and the log now reads as the history of a secure building. The way that lock actually opens is a bump key, and no amount of pulling will ever find it.

The apparatus you build to catch yourself is the part nobody audits. An error there is invisible, because its output is reassurance.

## The one-line fix, and what it actually bought

Round 8 changed one thing. Hold the violence positions fixed. Permute only the dissent.

That null asks the question the statistic was built for. Given where the violence actually is in this text, is the dissent nearer to it than chance? It preserves the comparison set's real arrangement and randomises only the thing under test.

The new statistic pools across texts. For each dissent hit, take the fraction of that text's positions lying at least as close to a violence hit. Average it. Call it U.

U is exactly 0.5 under random placement. Whatever the text length. However clustered the violence is. Below 0.5 is Girard's prediction.

| tier | texts | hits | U | null mean | p |
|---|---|---|---|---|---|
| **GOSPEL** | 4 | 112 | **0.4171** | 0.5018 | **0.0015** |
| TRAGEDY | 23 | 235 | 0.4838 | 0.5025 | 0.161 |
| MYTH | 50 | 334 | 0.4832 | 0.5018 | 0.124 |

First positive localization result in eight rounds. In the four Gospels, dissent vocabulary sits closer to violence vocabulary than chance places it.

<svg viewBox="0 0 760 190" width="100%" style="max-width:760px;height:auto;display:block;margin:2rem auto" role="img" aria-label="A number line where 0.5 is chance. The Gospel point sits clearly left of its null band at 0.4171. Tragedy and myth sit inside theirs at 0.484.">
<defs><marker id="a64" markerWidth="9" markerHeight="9" refX="8" refY="3" orient="auto"><path d="M0,0 L8,3 L0,6 z" fill="currentColor"/></marker></defs>
<line x1="100" y1="150" x2="660" y2="150" stroke="currentColor" stroke-width="1.2" opacity="0.5"/>
 <line x1="453" y1="34" x2="453" y2="150" stroke="currentColor" stroke-width="1.4" stroke-dasharray="4 4" opacity="0.6"/>
 <text x="453" y="168" fill="currentColor" font-size="12" text-anchor="middle" font-family="inherit" opacity="0.8">0.50 &#183; chance</text>
 <text x="120" y="168" fill="currentColor" font-size="12" text-anchor="middle" font-family="inherit" opacity="0.6">0.40</text>
 <line x1="88.99430000000001" y1="52" x2="264.9943" y2="52" stroke="currentColor" stroke-width="7" opacity="0.18" stroke-linecap="round"/><circle cx="176.9943" cy="52" r="5.5" fill="#e03131"/><text x="80" y="57" fill="currentColor" font-size="13" text-anchor="end" font-family="inherit">GOSPEL</text><text x="700" y="57" fill="#e03131" font-size="12.5" font-family="inherit">0.4171 &#183; p 0.0015</text>
 <line x1="338.30539999999996" y1="90" x2="460.30539999999996" y2="90" stroke="currentColor" stroke-width="7" opacity="0.18" stroke-linecap="round"/><circle cx="399.30539999999996" cy="90" r="5.5" fill="currentColor"/><text x="80" y="95" fill="currentColor" font-size="13" text-anchor="end" font-family="inherit">TRAGEDY</text><text x="700" y="95" fill="currentColor" font-size="12.5" font-family="inherit">0.4838 &#183; p 0.161</text>
 <line x1="344.30559999999997" y1="128" x2="450.30559999999997" y2="128" stroke="currentColor" stroke-width="7" opacity="0.18" stroke-linecap="round"/><circle cx="397.30559999999997" cy="128" r="5.5" fill="currentColor"/><text x="80" y="133" fill="currentColor" font-size="13" text-anchor="end" font-family="inherit">MYTH</text><text x="700" y="133" fill="currentColor" font-size="12.5" font-family="inherit">0.4832 &#183; p 0.124</text>
 <text x="380" y="24" fill="currentColor" font-size="12.5" text-anchor="middle" font-family="inherit" opacity="0.8">below 0.50 is Girard's prediction. the pale band is where chance puts it.</text>
</svg>
And then the round takes most of it back, and this is why the post does not end at the table.

The dissent lexicon was built in two halves, and one of them was disclosed in July as at higher risk of being motivated. Score the *core* half alone, the concepts that state Girard's actual claim, innocence and false witness and protest and plead:

```
full lexicon :  GOSPEL 0.4171  <  MYTH 0.4832  <  TRAGEDY 0.4838
core lexicon :  TRAGEDY 0.4838 <  MYTH 0.5053  <  GOSPEL 0.5143
```

The Gospels go from lowest to highest. On the concepts that carry Girard's claim they show no co-location at all, and sit fractionally farther from violence than chance. The entire effect belongs to the other half. Crowd speech. Division, some said, others said, not all.

So the surviving sentence is smaller than the one I set out to test. The Gospels put crowd-division language near violence language more than chance does. Myth and tragedy do not, and the concepts that state Girard's claim do not, in any tier.

I had written a falsifier for exactly that reversal. It was called N3.

It did not fire. I coded it as a comparison of two booleans rather than two orderings. Both orderings failed their own strict test, both booleans came out `False`, `False == False` returned `True`, and the script printed *core order matches full lexicon: yes*.

N3 fires in this post because I read the table underneath it.

A falsifier stated correctly and coded incorrectly is worse than no falsifier at all. No falsifier leaves you knowing you have no protection. A broken one prints reassurance, in the same font, in the same place, at the same time.

<svg viewBox="0 0 760 96" width="100%" style="max-width:760px;height:auto;display:block;margin:2rem auto" role="img" aria-label="The refrain, set alone: a check that cannot fail prints reassurance.">
<defs><marker id="a65" markerWidth="9" markerHeight="9" refX="8" refY="3" orient="auto"><path d="M0,0 L8,3 L0,6 z" fill="currentColor"/></marker></defs>
<rect x="0" y="12" width="760" height="70" fill="currentColor" fill-opacity="0.07"/>
 <line x1="0" y1="12" x2="760" y2="12" stroke="currentColor" stroke-width="2"/>
 <line x1="0" y1="82" x2="760" y2="82" stroke="currentColor" stroke-width="2"/>
 <text x="380" y="57" fill="currentColor" font-size="21" text-anchor="middle" font-family="inherit" font-weight="600">A check that cannot fail prints reassurance.</text>
</svg>
## What to take

Fill in the three-row table before you write the null, not after you read the result.

Then go and look at the part of your method you did not think was under test. Not the hypothesis, which you already doubt. The control. The baseline. The sanity check that has passed every time you have ever run it.

Mine had. Every time.

---

*Next: the rest of the arithmetic, all of it. Medians, one-sided p, where 0.05 came from, the Mann-Whitney U, and the power falsifier that fired at a median z of −0.012 and stopped a round from claiming an absence it could not have seen.*
