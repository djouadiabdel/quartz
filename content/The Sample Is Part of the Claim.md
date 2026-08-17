---
title: The Sample Is Part of the Claim
---

A good instrument pointed at the wrong texts produces excellent numbers about nothing. Almost nobody checks which texts.

Three things get confused, and the confusion is invisible from inside a spreadsheet.

| | in this project |
|---|---|
| **population** | all Greek and Roman narrative literature |
| **sampling frame** | what two websites and Project Gutenberg happen to hold, in English translation |
| **sample** | 76 texts, later 98 |

> **Every claim you make is about the population. Every number you have is about the sample.** The frame is the gap between them, and it is almost never examined.

<svg viewBox="0 0 760 250" width="100%" style="max-width:760px;height:auto;display:block;margin:2rem auto" role="img" aria-label="Three nested circles. The population is all Greek and Roman narrative literature; the sampling frame is what two websites happen to hold in English translation; the sample is a small dot inside. The ring between population and frame is shaded and labelled never measured.">
<defs><marker id="a51" markerWidth="9" markerHeight="9" refX="8" refY="3" orient="auto"><path d="M0,0 L8,3 L0,6 z" fill="currentColor"/></marker></defs>
<circle cx="290" cy="125" r="112" fill="currentColor" fill-opacity="0.10" stroke="currentColor" stroke-width="1.6"/>
 <circle cx="290" cy="125" r="66" fill="var(--light,#fff)" fill-opacity="0" stroke="currentColor" stroke-width="1.6"/>
 <circle cx="290" cy="125" r="66" fill="currentColor" fill-opacity="0"/>
 <circle cx="290" cy="140" r="13" fill="currentColor" fill-opacity="0.85"/>
 <g fill="currentColor" font-family="inherit" font-size="13">
  <text x="430" y="46" font-weight="600">POPULATION</text>
  <text x="430" y="65" font-size="12.5" opacity="0.85">all Greek and Roman narrative literature</text>
  <text x="430" y="112" font-weight="600">SAMPLING FRAME</text>
  <text x="430" y="131" font-size="12.5" opacity="0.85">what two websites and Gutenberg happen to hold,</text>
  <text x="430" y="148" font-size="12.5" opacity="0.85">in English translation, out of copyright</text>
  <text x="430" y="192" font-weight="600">SAMPLE</text>
  <text x="430" y="211" font-size="12.5" opacity="0.85">76 texts</text>
 </g>
 <line x1="290" y1="13" x2="290" y2="59" stroke="#e03131" stroke-width="2" marker-start="url(#at51)" marker-end="url(#at51)"/>
 <text x="276" y="36" fill="#e03131" font-size="12" text-anchor="end" font-family="inherit" font-weight="600">never</text>
 <text x="276" y="52" fill="#e03131" font-size="12" text-anchor="end" font-family="inherit" font-weight="600">measured</text>
 <text x="290" y="240" fill="currentColor" font-size="12.5" text-anchor="middle" font-family="inherit" opacity="0.75">every claim is about the outer ring. every number is about the dot.</text>
</svg>
## What the frame here actually was

Stated as biases rather than as a method, because that is what it is.

| the frame is biased toward | consequence |
|---|---|
| texts old enough to be out of copyright | translations are 1900 to 1921, not modern |
| texts somebody bothered to digitise | the canonical and the famous |
| texts with an English translation at all | fragments and minor works vanish |
| **whatever one website's page structure let a script fetch** | **this produced two silent bugs** |

Dwell on the last row. The sampling frame was partly determined by **HTML**. Not by scholarship. Not by a research design. By how a website laid out its pages, and by whether a script followed a link.

Truman is the anchor and he is the right one, because notice what would not have helped him. More observations would not have helped. Better records would not have helped. Every measurement he ever made inside Seahaven was accurate. A corpus is Seahaven, and every statistic computed on it is honest, and the frame has no visible edge from inside.

## Who is in it

The names run through the rest of the series, so here they are once with dates.

| name | when | what it is |
|---|---|---|
| **Homer** | c. 8th c. BC | the *Iliad* and the *Odyssey*, Greek epic verse |
| **Aeschylus, Sophocles, Euripides** | 5th c. BC | Athenian tragedy, written for the stage |
| **Diodorus Siculus** | 1st c. BC | a universal history whose early books retell myth as history |
| **Ovid** | AD 8 | the *Metamorphoses*, myth as a chain of transformations |
| **Seneca** | c. AD 50 | Roman tragedy in Latin, on the same Greek stories |
| **Apollodorus** | 1st-2nd c. AD | the *Bibliotheca*, a bare prose catalogue of the whole of Greek myth |
| **Hyginus** | c. 2nd c. AD | the *Fabulae*, the same idea and even more compressed |
| **Statius, Apollonius, Quintus Smyrnaeus** | 1st-4th c. AD | later epic, filling gaps the earlier poems left |

The split that matters is verse against prose. Homer, Euripides and Ovid are poets writing to be performed or read as poetry. Apollodorus and Hyginus are writing handbooks.

That is the split the project calls **epic against mythography**. [[Ten Rounds and the Half That Never Carried Anything|Post 9]] turns on it, because one whole result exists only because the epic texts drag their tier down.

## The play with its sacrifice removed

The fetcher never followed pagination. Theoi splits long pages and links the remainder as `CONTINUED`. One text hit the split.

| text | as scored | actual | missing |
|---|---|---|---|
| `seneca_hercules_oetaeus` | 11,119 words | 20,621 | **46%** |

The missing half is not arbitrary. The file broke off after Hyllus' speech, so Deianira's death, Hercules on the pyre and the apotheosis were all absent. Hercules spoke exactly one line in the file. Alcmena and Philoctetes never appeared at all.

The scorer was reading a play with its sacrifice removed. In a project about sacrifice.

<svg viewBox="0 0 760 190" width="100%" style="max-width:760px;height:auto;display:block;margin:2rem auto" role="img" aria-label="Seneca's Hercules Oetaeus as a bar split at fifty-four percent. The missing forty-six percent is greyed out and contains Deianira's death, Hercules on the pyre and the apotheosis. The truncated version still scored, and sat mid-table unremarked.">
<defs><marker id="a52" markerWidth="9" markerHeight="9" refX="8" refY="3" orient="auto"><path d="M0,0 L8,3 L0,6 z" fill="currentColor"/></marker></defs>
<rect x="60" y="34" width="346" height="44" fill="currentColor" fill-opacity="0.65" stroke="currentColor" stroke-width="1.3"/>
 <rect x="406" y="34" width="294" height="44" fill="none" stroke="currentColor" stroke-width="1.3" stroke-dasharray="5 4" opacity="0.55"/>
 <g fill="currentColor" font-family="inherit" font-size="12.5">
  <text x="233" y="61" text-anchor="middle" font-weight="600">11,119 words &#183; what the scorer read</text>
  <text x="553" y="55" text-anchor="middle" opacity="0.7">9,502 words the scorer never saw</text>
  <text x="553" y="73" text-anchor="middle" opacity="0.7" font-size="11.5">Deianira's death &#183; Hercules on the pyre &#183; the apotheosis</text>
  <text x="60" y="24" font-size="12" opacity="0.65">Seneca, Hercules Oetaeus</text>
  <text x="700" y="24" font-size="12" opacity="0.65" text-anchor="end">46% missing</text>
 </g>
 <text x="60" y="110" fill="currentColor" font-size="13" font-family="inherit">the half-play still produced a score, and the score looked ordinary:</text>
 <rect x="60" y="124" width="640" height="30" fill="currentColor" fill-opacity="0.06" stroke="currentColor" stroke-width="1"/>
 <text x="380" y="144" fill="currentColor" font-size="12.5" text-anchor="middle" font-family="inherit">sat mid-table in the results file &#183; nothing flagged it</text>
 <text x="60" y="176" fill="#e03131" font-size="12.5" font-family="inherit" font-weight="600">a missing text is visible. a half-text scores.</text>
</svg>
> **This is worse than a missing text. A missing text is visible. A half-play still scores**, and the score looks ordinary. It sat mid-table and nothing flagged it.

And it was nearly missed twice. The diagnostic that found it had classified the string `CONTINUED` as a phantom one-off speaker and dropped it into a list of ignored singletons. The pagination marker was in the very first diagnostic output and got read past twice before anyone saw what it meant.

One more thing belongs here because it cuts against the story. The first pass claimed five truncated files. That was wrong. The search was case-insensitive and had matched the ordinary word *continued* in prose. Only one text was affected.

> **A correction that overstates its own scope is not a correction.**

Then the rescore, and it went the wrong way. Restoring the pyre made the text score **lower**, 15.12 to 14.67, because the restored half is largely lament and apotheosis and lament dilutes a rate. The expectation had been the opposite. No verdict changed.

## The page that was found, and left out

The same audit turned up `DiodorusSiculus4D`, a real page absent from the fetcher's page list. It was fetched. It is on disk. It is excluded.

The reason matters more than the text does.

Diodorus is mythography, which is the group the failing prediction lost to. Fold the page in:

```
MYTHOGRAPHY  13.95 -> 13.67      vs  TRAGEDY 13.88
P1           FAIL             ->  PASS
```

A text discovered after seeing the results, added to the comparison group, flips a failed pre-registered prediction into a passing one.

Every step of that is defensible. It is a real page. It was missed by a genuine bug. Adding it makes the corpus more complete, which is unambiguously better. A reviewer would approve each move.

> **None of it felt like cheating, and that is exactly why the rule has to be mechanical rather than a matter of judgement.**

So the page sits on disk, unused, available to any future round whose predictions are committed before it is scored. The rule the project wrote for the lexicon binds the corpus identically. **The sample is part of the registration.**

## And nobody ever counted it

This one was found late, in a consistency pass, and it is the quietest failure in the project.

The corpus has four different sizes depending on where you look.

| where | what it says |
|---|---|
| `corpus2/` on disk | **76 files** |
| `results_corpus2_v2.csv` | **76 rows** |
| `PREREGISTRATION-2.md` and `RESULTS-2.md` | **71** scoreable |
| the same `RESULTS-2.md`, two paragraphs apart | **"35 of 72"** and **"7 of 72"** |

Three stated values and one real one, in files written by the same person in the same week.

Now derive the number that should be there. The pre-registration declared an 800-word minimum. Exactly three texts fall under it.

| text | words |
|---|---|
| `hyginus_fabulae_2` | 613 |
| `hyginus_fabulae_3` | 685 |
| `hyginus_fabulae_4` | 771 |

76 minus 3 is **73**.

<svg viewBox="0 0 760 178" width="100%" style="max-width:760px;height:auto;display:block;margin:2rem auto" role="img" aria-label="Four numbers for the size of the same corpus: seventy-six files on disk, seventy-one in the pre-registration, seventy-two two paragraphs later in the same file, and seventy-three which is derivable from the project's own eight-hundred-word rule and is written down nowhere.">
<defs><marker id="a53" markerWidth="9" markerHeight="9" refX="8" refY="3" orient="auto"><path d="M0,0 L8,3 L0,6 z" fill="currentColor"/></marker></defs>
<g font-family="inherit" text-anchor="middle">
  <text x="120" y="70" fill="currentColor" font-size="52" font-weight="600">76</text>
  <text x="330" y="70" fill="currentColor" font-size="52" font-weight="600" opacity="0.55">71</text>
  <text x="530" y="70" fill="currentColor" font-size="52" font-weight="600" opacity="0.55">72</text>
  <text x="700" y="70" fill="#e03131" font-size="52" font-weight="600">73</text>
  <g font-size="12" fill="currentColor" opacity="0.8">
   <text x="120" y="94">files on disk,</text><text x="120" y="110">rows in the CSV</text>
   <text x="330" y="94">"scoreable", in the</text><text x="330" y="110">pre-registration</text>
   <text x="530" y="94">two paragraphs later,</text><text x="530" y="110">in the same file</text>
  </g>
  <g font-size="12" fill="#e03131" font-weight="600">
   <text x="700" y="94">derivable, and</text><text x="700" y="110">written down nowhere</text>
  </g>
  <text x="380" y="150" fill="currentColor" font-size="12.5" opacity="0.85">76 minus the 3 texts under the project's own 800-word minimum</text>
  <text x="380" y="168" fill="currentColor" font-size="12" opacity="0.65">613, 685 and 771 words. nothing is falsified. nobody ever counted.</text>
 </g>
</svg>
**73 is the one number never written down anywhere in the project.** It is also, as it happens, the n of the density correlation reported in a later round.

Nothing is falsified by this. No verdict moves.

The point is smaller and worse. The sample was never counted against its own stated rule. By anybody, for eight rounds, in a project whose entire defence is that its sample was fixed in advance.

You can check this yourself in under a minute. Count the files. Count the rows in the CSV. Read the two paragraphs. The whole thing is on disk.

And it connects to something already known and recorded: a later round silently readmitted those same three short texts, dropping the 800-word minimum without declaring it. The rule was broken two weeks after it was written, by the same project, and caught nothing until somebody went looking.

## Two bugs with the same shape

There is a second fetcher bug in this project, in a different study, and putting it next to the first one produces the only generalisable thing in this post.

The conversion instrument's fetcher scraped a book list off Project Gutenberg by anchoring on a string in the page, then reading forward to the next heading. Gutenberg moved that string. It now appears first in a navigation link near the top of the page, so the scraper anchored there instead, and the heading that stopped it arrived 204 characters later, before a single list item.

The old anchor returned **zero rows**. The new one returns a hundred.

And the study's own results file had recorded the symptom as *the fetch was killed partway through*, which was wrong. The fetch completed. It completed and returned nothing, and nothing looked enough like an interruption that nobody checked.

Now put the two side by side.

| | what it did | what it should have done |
|---|---|---|
| the pagination bug | returned half a play | error, or return the whole play |
| the anchor bug | returned zero books | error, or return a hundred books |

> **Neither bug crashed. Both produced output that looked like output.** A half-play scores mid-table. An empty list looks like a fetch that stopped early.

That is the property worth carrying out of this post, because it is the same property [[Four Broken Nulls One Mistake|post 6]] finds in the control tests and [[A Check That Cannot Fail Prints Reassurance|post 10]] finds in the validation checks. The dangerous failures in this project have never been the ones that threw an exception.

They have all been the ones that **returned a plausible value.**

An exception is a gift. It stops you and it points at a line number. A plausible wrong value goes into a CSV, gets averaged with correct ones, and comes out the other end as a result with four significant figures on it.

And the defence against that class is not more care. Care is what everybody thinks they are already applying. The defence is an integrity check that runs over the data and knows what the data is supposed to look like, and this project has been recommending one to itself since July without building it.

## What this costs

Not a result. That is the honest and slightly deflating summary of this whole post. The truncation changed no verdict. The Diodorus page was excluded. The count discrepancy moves nothing.

What it costs is a class of confidence.

Every one of these was found by accident, on the way to something else. The speaker diagnostic found the truncation while looking for victim voice share. The consistency pass found the count while checking cross-references.

None of the project's checks was pointed at the corpus. The corpus is data, and data is the part you fix once and then stop thinking about.

> **No integrity check has ever run over this corpus.** A truncated text is invisible to every metric the project computes.

That recommendation was written into the correction file in July. It is still unbuilt, and it is now two for two on catching things nobody was looking for.

[[Four Broken Nulls One Mistake|Post 6]] is what happens when the same inattention lands on the control tests instead of the data.
