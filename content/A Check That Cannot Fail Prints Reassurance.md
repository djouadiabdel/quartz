---
title: A Check That Cannot Fail Prints Reassurance
---

This is the sentence the whole project turns on, and it has to fire on the project itself or it is a slogan.

> **A check that cannot fail prints reassurance.**

Four instances follow. Three are mine and one is in the toolchain that checks the writing about the other three.

## 1. The check that certifies the headline metric

Round 2 needed to establish that MIN, the minimum across the four buckets, actually carries information rather than sitting at zero everywhere. So it wrote a validation check, called P6, and P6 asked this:

**What share of texts have MIN above zero?**

Answer: 90.3%. Nine texts in ten produce a non-zero minimum, so the metric is alive. P6 passed, MIN was certified, and every later round quoted it.

Now round 10, fourteen months of project time later. Delete the word `death`, which is 61.9% of the `crisis` bucket, and watch what happens to the metric P6 certified.

| what happened to MIN | |
|---|---|
| mean | 0.876 → **0.566**, a fall of **35.4%** |
| median | 0.818 → 0.515 |
| texts with MIN exactly zero | 7 → **7** |
| **share non-zero, which is what P6 measures** | **90.4% → 90.4%** |

**A third of the metric is gone and P6 reports zero movement.** Not a small movement. Zero. To one decimal place, in the direction of nothing at all.

<svg viewBox="0 0 760 238" width="100%" style="max-width:760px;height:auto;display:block;margin:2rem auto" role="img" aria-label="A fuel gauge with only two positions, empty and not empty, reads identically whether the tank is at two thirds or one third. A continuous gauge shows the fall. P6 is the two-position gauge.">
<defs><marker id="a101" markerWidth="9" markerHeight="9" refX="8" refY="3" orient="auto"><path d="M0,0 L8,3 L0,6 z" fill="currentColor"/></marker></defs>
<g fill="none" stroke="currentColor" stroke-width="1.6">
  <rect x="40" y="46" width="300" height="58" rx="4"/><rect x="40" y="126" width="300" height="58" rx="4"/>
  <rect x="430" y="46" width="290" height="58" rx="4"/><rect x="430" y="126" width="290" height="58" rx="4"/>
 </g>
 <rect x="432" y="48" width="190" height="54" fill="currentColor" fill-opacity="0.6"/>
 <rect x="432" y="128" width="95" height="54" fill="currentColor" fill-opacity="0.6"/>
 <g fill="currentColor" font-family="inherit" text-anchor="middle">
  <text x="190" y="30" font-size="12.5" font-weight="600">the binary gauge</text>
  <text x="575" y="30" font-size="12.5" font-weight="600">a gauge that can see the slope</text>
  <text x="190" y="82" font-size="17" font-weight="600">NOT EMPTY</text>
  <text x="190" y="162" font-size="17" font-weight="600">NOT EMPTY</text>
  <text x="575" y="82" font-size="15" font-weight="600">two thirds</text>
  <text x="575" y="162" font-size="15" font-weight="600">one third</text>
  <text x="380" y="212" font-size="12.5" opacity="0.9">MIN's mean fell <tspan font-weight="600">35.4%</tspan>. P6 moved <tspan font-weight="600" fill="#e03131">0.0 percentage points</tspan>.</text>
  <text x="380" y="230" font-size="12" opacity="0.7">it watches the cliff. everything that matters happens on the slope.</text>
 </g>
 <text x="26" y="82" fill="currentColor" font-size="11.5" text-anchor="end" font-family="inherit" opacity="0.7">before</text>
 <text x="26" y="162" fill="currentColor" font-size="11.5" text-anchor="end" font-family="inherit" opacity="0.7">after</text>
</svg>
The reason is structural and it is not subtle once you see it. P6 asks a yes-or-no question. Is the minimum above zero. Deleting `death` did not push any bucket to exactly zero. It made `crisis` much smaller on forty-four texts.

> **P6 watches the cliff. Everything that matters happens on the slope.**

So P6 is a check that certifies MIN and is structurally incapable of detecting the largest change ever made to MIN. It has never failed. It cannot fail in the way that matters. It passed at 90.3% in July and it will pass at 90-something for as long as anybody runs it.

Two consequences, both against me.

**Every "MIN non-zero" figure in the record is weaker than it reads**, including round 2's 90.3% and round 9's 89.0%. Anyone citing those numbers, including me in five earlier documents, was citing a quantity that moves only in the extreme.

**And my own predictions inherited the defect.** Round 10's D2 and D5 were written using the same non-zero share, because that was the established measure. So the falsifier F1 fired, correctly, on a prediction I had built out of the exact flaw the round went on to discover.

The round failed by inheriting the defect it found. That is reported rather than tidied, and the corrected comparison sits next to the failed one rather than replacing it. On a measure that can see magnitude, deleting `death` does roughly **a hundred times** the damage that deleting `king` did.

## 2. The falsifier that compared two booleans

Round 8 produced the project's first positive localization result. It also carried a falsifier called N3, written in advance. **If the `core` half reverses the tier ordering, the result belongs in the headline rather than a footnote.**

N3 was the correct falsifier. It was pointed at the right thing. And here is how it was coded.

```python
corder == u2        # comparing two booleans
```

Both orderings failed their own strict test. So both variables were `False`. So `False == False` returned `True`. So the script printed:

```
core order matches full lexicon? yes
```

The reversal was total. On the full lexicon the Gospels are lowest of three tiers, which is Girard's prediction. On `core` they are highest. The script looked at that and reported a match.

> **A falsifier stated correctly and coded incorrectly is worse than no falsifier at all.** No falsifier leaves you knowing you are unprotected. A broken one prints reassurance, in the same font, in the same place, at the same time.

It fired anyway, because the numbers were printed in a table directly underneath, and somebody read the table.

## 3. The audit that could not report the defect it detected

The series built from this project has a script, `audit.py`, that checks every episode for mechanical problems. Too short. Too long. Missing sections.

It printed this, on screen, correctly:

```
<-- OVERLONG, split it
```

And then the summary line said:

```
NO MECHANICAL DEFECTS FOUND
```

Both, at once, with an 1,855-word episode named on the screen between them. The overlong branch printed a warning and never called the function that registers a defect. Only the too-short branch did.

<svg viewBox="0 0 760 220" width="100%" style="max-width:760px;height:auto;display:block;margin:2rem auto" role="img" aria-label="A warning lamp is lit but its wire to the status readout is broken, so the readout says all systems normal. That is the audit script printing OVERLONG and reporting no defects.">
<defs><marker id="a102" markerWidth="9" markerHeight="9" refX="8" refY="3" orient="auto"><path d="M0,0 L8,3 L0,6 z" fill="currentColor"/></marker></defs>
<circle cx="200" cy="70" r="30" fill="#e03131" fill-opacity="0.75" stroke="currentColor" stroke-width="1.6"/>
 <text x="200" y="122" fill="currentColor" font-size="12.5" text-anchor="middle" font-family="inherit">the lamp is lit</text>
 <text x="200" y="140" fill="currentColor" font-size="11.5" text-anchor="middle" font-family="inherit" opacity="0.75">&lt;-- OVERLONG, split it</text>
 <path d="M234,70 L300,70" stroke="currentColor" stroke-width="2"/>
 <path d="M340,70 L400,70" stroke="currentColor" stroke-width="2"/>
 <g stroke="#e03131" stroke-width="3" stroke-linecap="round">
  <path d="M306,56 L334,84"/><path d="M334,56 L306,84"/>
 </g>
 <text x="320" y="112" fill="#e03131" font-size="11.5" text-anchor="middle" font-family="inherit" font-weight="600">not wired</text>
 <rect x="400" y="42" width="300" height="56" rx="4" fill="currentColor" fill-opacity="0.08" stroke="currentColor" stroke-width="1.6"/>
 <text x="550" y="76" fill="currentColor" font-size="14" text-anchor="middle" font-family="inherit" font-weight="600">NO MECHANICAL DEFECTS FOUND</text>
 <text x="550" y="122" fill="currentColor" font-size="12.5" text-anchor="middle" font-family="inherit">the summary the reader sees</text>
 <text x="380" y="184" fill="currentColor" font-size="12.5" text-anchor="middle" font-family="inherit" opacity="0.9">both printed, at once, with an 1,855-word episode named on the screen between them</text>
 <text x="380" y="204" fill="currentColor" font-size="12" text-anchor="middle" font-family="inherit" opacity="0.7">the branch printed a warning and never registered a defect</text>
</svg>
And there was a second one in the same file. The check verifying that each episode carries all six required structural elements looked for the word *anchor* and a Questions heading, and nothing else. Sixteen episodes were missing a falsifier section or a hand-off, and the audit reported no defects on all sixteen.

That is this series' own refrain firing on the toolchain built to enforce it. The script whose job is to say no had two branches where it could only say yes.

## 4. The floor nobody computed

This one is different from the other three. Nothing is broken. Every number is correct. And it may be the most expensive of the four.

Round 2 ran a translation control. Two English translations of the same play, *Agamemnon*, scored on the same four buckets. The question was how much of a score is the text and how much is the translator.

**They came out 17.2% apart.** That passed, and it was reported as a pass, and it should have been.

Round 6 repeated it on a different construct with the ASV and KJV Gospels, two translations 290 years apart. **20.4%.**

So the instrument's own wobble, measured twice, is somewhere around 17 to 20 percent. Below that, a difference between two texts is not distinguishable from a difference between two translators.

Now go and look at what the project spent three rounds arguing about.

The comparison it kept returning to was mythography against tragedy. Does the bare catalogue of myth score differently from the plays?

| | |
|---|---|
| MYTHOGRAPHY | **13.95** |
| TRAGEDY | **13.88** |
| the gap | **0.5%** |

<svg viewBox="0 0 760 196" width="100%" style="max-width:760px;height:auto;display:block;margin:2rem auto" role="img" aria-label="A ruler whose smallest gradation is 17.2 percent, the instrument's measured wobble. The 0.5 percent gap the project argued about for three rounds is drawn to scale inside the first tick and is essentially invisible.">
<defs><marker id="a103" markerWidth="9" markerHeight="9" refX="8" refY="3" orient="auto"><path d="M0,0 L8,3 L0,6 z" fill="currentColor"/></marker></defs>
<line x1="60" y1="96" x2="700" y2="96" stroke="currentColor" stroke-width="2"/>
 <g stroke="currentColor" stroke-width="2">
  <line x1="60" y1="96" x2="60" y2="66"/><line x1="220" y1="96" x2="220" y2="66"/>
  <line x1="380" y1="96" x2="380" y2="66"/><line x1="540" y1="96" x2="540" y2="66"/><line x1="700" y1="96" x2="700" y2="66"/>
 </g>
 <g fill="currentColor" font-size="12" text-anchor="middle" font-family="inherit" opacity="0.8">
  <text x="60" y="56">0</text><text x="220" y="56">17.2%</text><text x="380" y="56">34.4%</text><text x="540" y="56">51.6%</text><text x="700" y="56">68.8%</text>
 </g>
 <text x="380" y="32" fill="currentColor" font-size="12.5" text-anchor="middle" font-family="inherit" opacity="0.85">one tick = the smallest difference this instrument may have an opinion about</text>
 <rect x="60" y="102" width="4.7" height="22" fill="#e03131"/>
 <path d="M62,140 L62,128" stroke="#e03131" stroke-width="1.6" marker-end="url(#at103)"/>
 <text x="70" y="156" fill="#e03131" font-size="12.5" font-family="inherit" font-weight="600">0.5%</text>
 <text x="70" y="174" fill="#e03131" font-size="12" font-family="inherit">mythography 13.95 against tragedy 13.88, argued about across three rounds</text>
</svg>
**A 0.5% gap, inside a 17% noise floor.**

Nobody put those two numbers next to each other. The translation control was filed as a gate, something the instrument had to pass in order to proceed. It is not a gate. It is a **ruler**, and it tells you the smallest difference this instrument is entitled to have an opinion about.

Both numbers were in the repository. Both were correct. They were four files apart and nobody walked between them. So a difference the instrument cannot resolve got argued about across three rounds and two seasons of writing.

And the ruler itself rests on **one pair of translations of one play**. Nothing else in the entire project rests on a sample of one, except the thing everything else rests on.

## Why none of these look like mistakes from inside

Each of the four was written by somebody who could have explained, correctly, what the check was for. None is a slip. That is the part worth sitting with, because the obvious lesson from this post is *be more careful*, and being more careful would have prevented none of them.

Take P6 as the clean case.

The question it asks is a **good** question. Does the minimum carry information, or is it pinned at the floor? That is exactly the right worry about a minimum, it is the worry [[The Arithmetic All of It|post 7]] spends a whole section on, and P6 was written to answer it.

The defect is not in the question. It is in the answer being **binary** when the quantity is **continuous.** Somebody converted *does the metric carry information* into *is it above zero*, which is a reasonable thing to do at the moment you do it, because at that moment you are worried about the floor and the floor is exactly where zero is.

Then the worry changed and the check did not.

> **A check is written to answer the worry you had on the day you wrote it.** It goes on answering that one long after the project has moved to a different worry, and nothing about the output tells you which question is being answered.

The same shape holds for the other three. N3's author knew what a reversal was and wrote a correct description of one. The audit's author knew that overlong episodes matter, and printed a message saying so. The translation control's author knew that a 17.2% wobble was worth measuring, which is why it got measured at all.

In every case the thinking was done. What failed was the step after the thinking, where a correct idea becomes a line of code or a number in a file and quietly loses a property on the way.

That step has no ceremony attached to it. Nobody reviews it. It is the least interesting part of the work and it is where all four of these live.

## What the four have in common

None of them crashed. That is the property.

A broken hypothesis test gives you a number you can argue with. A broken check gives you a green light, and a green light is not an argument, it is a permission to stop looking.

| | what it was supposed to catch | what it could actually see |
|---|---|---|
| **P6** | MIN failing to carry information | only MIN hitting exactly zero |
| **N3** | the core half reversing the tiers | whether two booleans were equal |
| **audit.py** | episodes that are too long | nothing, the branch never registered |
| **the 17.2%** | translation artefacts | it saw them, and nobody read it as a limit |

And notice where all four live. Not in the hypothesis, which was doubted constantly, pre-registered, falsified, and reported when it failed. They live in the **apparatus built to do the doubting.**

> **The part of your method that exists to catch you is the part nobody audits**, and an error there is invisible, because its output is reassurance.

## How all four were actually caught

This is the practical part and it is the only advice in this post.

Not one of these was caught by a check. Every single one was caught by a human being reading a number printed next to a verdict, and noticing they disagreed.

P6 was caught because round 10 printed MIN's mean beside MIN's non-zero share. N3 was caught because the tier table sat directly under the line saying *matches*. The audit bug was caught because the warning text and the summary were on the same screen. The noise floor was caught because somebody put two files side by side.

So the rule is unglamorous and it is the one thing I would take from this whole project into any other:

> **Never print a verdict without printing the quantity it was computed from, directly beside it.**

A verdict alone is unfalsifiable by the reader. A verdict with its numbers underneath can be contradicted by its own evidence, on the same line, by somebody who is only half paying attention.

That is the entire mechanism by which this project caught itself four times. It is not rigour and it is not cleverness. It is refusing to summarise.

## And the demand

Go and find the check in your own work that has never failed.

Not the hypothesis. You already doubt that, and the doubt is why it is safe. The control. The baseline. The validation step. The green light you have never once seen go red.

Then ask the only question that matters about it: **what would have to be true for this to fail?**

If you cannot answer, it has not been passing. It has been printing.
