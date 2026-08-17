---
title: Turning Four Sentences Into Code
---

Girard names four marks the persecution mechanism leaves in a text. To measure them you need word lists, a way to count, and a way to turn four numbers into one.

Every one of those three steps is a decision about the theory disguised as a technical detail. This post is the three decisions.

## Why there is no stemming

Every tutorial tells you to stem. Reduce words to their roots so `murder`, `murders` and `murdered` all count once. One line of code, standard practice, obviously correct.

This project refused it entirely. No prefix matching anywhere.

Here is why, from the actual corpus.

| you stem | you also catch | how many times |
|---|---|---|
| `rend-` | render, rendered, rendering | 28 |
| `stone-` | stone the material, a stone wall, a stone tomb | 211 |
| `torn-` | tornado | |
| **`tear-`** | **tears, which is weeping** | **441** |

Read the last row slowly. The bucket exists to catch a body being torn apart by a crowd. Stemming hands it four hundred and forty-one instances of people crying.

<svg viewBox="0 0 760 268" width="100%" style="max-width:760px;height:auto;display:block;margin:2rem auto" role="img" aria-label="Four word stems drawn as funnels, with the accidental catch drawn to scale. Stemming tear- to catch tearing apart also catches four hundred and forty-one instances of the word tears, meaning weeping.">
<defs><marker id="a41" markerWidth="9" markerHeight="9" refX="8" refY="3" orient="auto"><path d="M0,0 L8,3 L0,6 z" fill="currentColor"/></marker></defs>
<g font-family="inherit"><path d="M60,30 L152,30 L116,74 L96,74 Z" fill="none" stroke="currentColor" stroke-width="1.5"/><rect x="96" y="74" width="20" height="10" fill="currentColor" fill-opacity="0.7"/><text x="106" y="22" fill="currentColor" font-size="13" text-anchor="middle" font-family="inherit" font-weight="600">rend-</text><text x="106" y="102" fill="currentColor" font-size="12.5" text-anchor="middle" font-family="inherit" font-weight="600">28</text><text x="106" y="119" fill="currentColor" font-size="11.5" text-anchor="middle" font-family="inherit" opacity="0.8">render, rendered</text><path d="M230,30 L322,30 L286,74 L266,74 Z" fill="none" stroke="currentColor" stroke-width="1.5"/><rect x="266" y="74" width="20" height="72" fill="currentColor" fill-opacity="0.7"/><text x="276" y="22" fill="currentColor" font-size="13" text-anchor="middle" font-family="inherit" font-weight="600">stone-</text><text x="276" y="164" fill="currentColor" font-size="12.5" text-anchor="middle" font-family="inherit" font-weight="600">211</text><text x="276" y="181" fill="currentColor" font-size="11.5" text-anchor="middle" font-family="inherit" opacity="0.8">a stone wall, a tomb</text><path d="M400,30 L492,30 L456,74 L436,74 Z" fill="none" stroke="currentColor" stroke-width="1.5"/><rect x="436" y="74" width="20" height="2" fill="currentColor" fill-opacity="0.7"/><text x="446" y="22" fill="currentColor" font-size="13" text-anchor="middle" font-family="inherit" font-weight="600">torn-</text><text x="446" y="94" fill="currentColor" font-size="12.5" text-anchor="middle" font-family="inherit" font-weight="600">6</text><text x="446" y="111" fill="currentColor" font-size="11.5" text-anchor="middle" font-family="inherit" opacity="0.8">tornado</text><path d="M570,30 L662,30 L626,74 L606,74 Z" fill="none" stroke="currentColor" stroke-width="1.5"/><rect x="606" y="74" width="20" height="150" fill="currentColor" fill-opacity="0.7"/><text x="616" y="22" fill="currentColor" font-size="13" text-anchor="middle" font-family="inherit" font-weight="600">tear-</text><text x="616" y="242" fill="currentColor" font-size="12.5" text-anchor="middle" font-family="inherit" font-weight="600">441</text><text x="616" y="259" fill="currentColor" font-size="11.5" text-anchor="middle" font-family="inherit" opacity="0.8">TEARS, i.e. weeping</text><text x="616" y="276" fill="#e03131" font-size="11.5" text-anchor="middle" font-family="inherit">in a violence bucket</text></g>
</svg>
And the deep problem is not the size of the error. It is the direction.

Weeping clusters in exactly the passages where a violence bucket is supposed to fire. Grief and killing occur in the same scenes. So the error is not noise scattered evenly across the corpus, it is a signal shaped like the thing being hunted.

> **A big random error is a problem you can see. A correlated error of any size is a result you cannot tell from a discovery.**

The clinical name for what a stemmer has is excellent sensitivity and terrible specificity. The character version is Drax, taking every phrase at its surface and processing it perfectly. Letters go in, the suffix rule applies, and the meaning was never involved.

So every concept lists its surface forms explicitly. `tear_apart` is exactly the strings that mean tearing apart, written out by hand.

| | explicit lists | stemming |
|---|---|---|
| false positives | few, each one traceable | many, and invisible |
| false negatives | **many.** Any form you forgot is silently missed | few |
| auditable | **yes.** Open the file and read it | no |
| effort | high | one line |

That is a trade and it should be presented as one. Explicit lists are not more accurate. They swap a loud checkable error for a quiet uncheckable one, and in a project whose entire defence is *go and check*, that is the right swap.

## Deleting 960 hits from your own instrument

Then I went through the lexicon deleting.

| removed | hits it was contributing | why |
|---|---|---|
| bare `cast`, `drive`, `driven` | **749 combined** | "cast a glance", "driven by the wind" |
| `tears`, `tearful` | **462** | weeping |
| bare `stone`, `stones` | **211** | a stone wall, a stone tomb |
| `render`, `rendered` | 28 | not rending |
| `ravishing` | | almost always "ravishing beauty" here |

Roughly 960 hits deleted from an instrument whose author wanted the numbers to come out a particular way.

That is the strongest evidence in the whole project that the lexicon was not tuned, and it is a kind that cannot be faked. You can claim you were careful. You cannot claim you deleted 960 hits from your own case unless the file shows it.

The rule that came out of it is a claim about English rather than about Girard. **The bare verb is noise. The verb plus its particle is the concept.** Claims like that decide results far more often than anybody admits.

And one honest hole, flagged rather than closed. Whether those 960 hits fell evenly across the corpus or disproportionately onto the control texts was never measured. If they fell on controls, deleting them is tuning wearing the costume of restraint.

## The refusal

Then the *Bacchae* failed.

Girard's own central example, the play where a crowd tears Pentheus apart, came back mid-table. The obvious repair was sitting in the project's own next-steps file: add dismemberment vocabulary to the `crimes` bucket so it catches him.

It was refused, and the reason is not statistical.

> In Girard the crime stereotype is **what the victim is accused of.** The tearing is **what the mob does.** Tearing belongs in violence. Putting it in crimes would have corrupted the bucket to pass a test.

The instrument was one line of reasoning away from being repaired to make its own failing example pass. What stopped it was a definitional distinction. Not a number.

The two fake rules in *Death Note* are the exact shape of what was avoided. A rule added to the notebook, in the same hand, on the same page, indistinguishable from the real ones once written. A lexicon is a rulebook, and it carries no record of when a line was added.

## The first number, and what it throws away

$$ r = 1000 \times \text{hits} / \text{total words} $$

Hits per thousand words. Prevalence, which is cases over population, and everybody already knows why the denominator matters. A bigger hospital has more infections and is not dirtier. A batting average divides by opportunity and nobody has ever needed that explained.

So the rate is the correct instinct correctly applied. This section is about what the correct instinct costs.

Take the *Bacchae*. Seventeen thousand words. Cut it into individual words, put them in a bag, shake it, pour them out in whatever order they come.

Now score it.

> **The number is identical. To the last decimal place.**

Not close. Identical, and not as a limitation of the implementation. It follows from the arithmetic with no room for anything else. The numerator counts hits and shuffling creates no hits. The denominator counts words and shuffling creates no words. Both terms depend on which words are present and on nothing else.

The rate cannot tell Euripides from a bag of the same words.

> **A rate treats a text as a bag of words.** So it can never test a claim about **where** something happens, **when**, or **what it happens near.**

Sit with what is inside the word *order*, because it sounds small. Order is adjacency, sequence, scene, episode. What happens next, and to whom, and what one passage does to the one after it. Order is the whole of narrative, and a rate discards all of it in a single division.

And Girard's claim, from [[Girard in the Minimum|post 2]], is that four stereotypes converge on **one passage**.

His claim is about a moment. A rate cannot represent a moment.

That mismatch causes every major failure in this project. Not a bug, not a bad word list, not too small a corpus. The instrument and the claim are about different kinds of thing, and no amount of extra data repairs it. A hundred more texts improve the precision of a quantity that does not contain the claim.

There is a second cost, subtler. A rate rewards density of event. Mythography runs **28.65 neutral event-words per thousand** against 21 to 23 for everything else, because Apollodorus is a handbook. He records what happened and drops everything a poet puts around it. Strip the lyric out of a text and its rate rises without a single new event being described.

None of which makes the rate worthless. It is the correct instrument for any question about **how much**. It has no free parameters. Two people scoring the same text get the same number to the last decimal, and that transparency is worth a great deal.

> The problem is not that the rate is a bad measurement. **It is a good measurement of the wrong quantity**, and those two failures look identical from inside the spreadsheet.

## Adding up against all four at once

Four numbers per text. You have to get to one, because you cannot rank texts or test a prediction against a quadruple.

$$ SUM = r_{crisis} + r_{crimes} + r_{marks} + r_{violence} $$
$$ MIN = \text{the smallest of the four} $$

SUM is accumulation. A text scores high by having a lot of any of it, and one enormous bucket carries the other three. Call that property by its name: **SUM is compensatory.** Strength in one place pays for absence in another and the total does not record which happened.

MIN is conjunction. A text scores only as high as its weakest stereotype. Drench a text in violence with no accusation anywhere and it scores zero.

| | crisis | crimes | marks | violence | **SUM** | **MIN** |
|---|---|---|---|---|---|---|
| Text A | 2.0 | 2.0 | 2.0 | 2.0 | **8.0** | **2.0** |
| Text B | 0.0 | 0.0 | 0.0 | 8.0 | **8.0** | **0.0** |

<svg viewBox="0 0 760 214" width="100%" style="max-width:760px;height:auto;display:block;margin:2rem auto" role="img" aria-label="Two invented texts with identical totals. Text A has all four stereotypes evenly. Text B has one enormous bucket and three empty ones. SUM reports them as identical; MIN separates them completely.">
<defs><marker id="a42" markerWidth="9" markerHeight="9" refX="8" refY="3" orient="auto"><path d="M0,0 L8,3 L0,6 z" fill="currentColor"/></marker></defs>
<g font-family="inherit"><rect x="150" y="32" width="120" height="34" fill="currentColor" fill-opacity="0.7" stroke="currentColor" stroke-width="1.2"/><rect x="270" y="32" width="120" height="34" fill="currentColor" fill-opacity="0.7" stroke="currentColor" stroke-width="1.2"/><rect x="390" y="32" width="120" height="34" fill="currentColor" fill-opacity="0.7" stroke="currentColor" stroke-width="1.2"/><rect x="510" y="32" width="120" height="34" fill="currentColor" fill-opacity="0.7" stroke="currentColor" stroke-width="1.2"/><rect x="150" y="104" width="480" height="34" fill="currentColor" fill-opacity="0.7" stroke="currentColor" stroke-width="1.2"/><text x="138" y="55" fill="currentColor" font-size="13" text-anchor="end">Text A</text><text x="138" y="127" fill="currentColor" font-size="13" text-anchor="end">Text B</text><g fill="currentColor" font-size="11.5" text-anchor="middle" opacity="0.9"><text x="210" y="54">2.0</text><text x="330" y="54">2.0</text><text x="450" y="54">2.0</text><text x="570" y="54">2.0</text><text x="390" y="126">8.0 &#183; all of it in violence</text></g><g fill="currentColor" font-size="12.5" font-family="inherit"><text x="648" y="46">SUM <tspan font-weight="600">8.0</tspan></text><text x="648" y="66">MIN <tspan font-weight="600">2.0</tspan></text><text x="648" y="118">SUM <tspan font-weight="600">8.0</tspan></text><text x="648" y="138" fill="#e03131">MIN <tspan font-weight="600">0.0</tspan></text></g><text x="390" y="184" fill="currentColor" font-size="12.5" text-anchor="middle" opacity="0.85">identical on SUM. as different as two texts can be on MIN.</text><text x="390" y="202" fill="currentColor" font-size="12" text-anchor="middle" opacity="0.65">Text B is a battle scene with no victim and no accusation in it anywhere</text></g>
</svg>
Identical on SUM, as different as two texts can be on MIN. Text A has all four stereotypes at once. Text B is a battle scene with no victim, no accusation and no crisis in it anywhere.

The table contains no information beyond the four columns. Both metrics see identical inputs, and everything separating the two verdicts happens in the choice of operation.

The clinical version is criteria requiring N of M against criteria requiring all of them. SIRS needs two of four and catches everything that walks through the door. A definition requiring all four is specific and misses cases. Neither is wrong. The question is never which is better, it is what the label is for.

MIN was chosen on theory alone, before any data recommended it.

If four stereotypes are four traces of one mechanism, then a text with three and not the fourth is evidence **against** the mechanism. Not weak evidence for it.

> **MIN is the algebraic form of "they appear together."** SUM is the algebraic form of "there is a lot of this stuff around."

## And the attribution was wrong

That reasoning is good. The sentence the project attached to it was not, and nobody checked for eight rounds.

Girard's own rule, from [[The Rule Girard Actually Wrote|post 3]], is *three are enough and often even two*. That is N-of-M. MIN demands four of four and returns zero on three.

| | |
|---|---|
| the reasoning | **still good.** Conjunction, not accumulation, is what makes it a theory |
| the attribution | **wrong.** Girard requires two, and nobody had read the sentence |
| what MIN is | **a deliberate strengthening**, which is legitimate to do and a different thing to claim |

Choosing a harder test than your source requires is defensible and often admirable. Presenting it as what the source requires is not.

## The dinner party that beat every tragedy

MIN was chosen on theory. Here is the case that vindicates it, from a text that was in the corpus to be boring.

| book | scene | crisis | crimes | marks | violence | **SUM** | **MIN** |
|---|---|---|---|---|---|---|---|
| **7** | Odysseus welcomed at the palace | 0.30 | 0.00 | **6.21** | **0.00** | **6.51** | **0.00** |
| 18 | Irus the beggar | 0.00 | 0.00 | 5.49 | 2.15 | 7.64 | **0.00** |
| 22 | the slaughter of the suitors | 1.09 | 0.22 | 0.22 | 4.14 | 5.67 | **0.22** |

<svg viewBox="0 0 760 196" width="100%" style="max-width:760px;height:auto;display:block;margin:2rem auto" role="img" aria-label="Three books of the Odyssey as stacked bars. Book seven, a dinner party, has one enormous marks bucket and outscores book twenty-two, a massacre, on SUM. On MIN the dinner party correctly scores zero.">
<defs><marker id="a43" markerWidth="9" markerHeight="9" refX="8" refY="3" orient="auto"><path d="M0,0 L8,3 L0,6 z" fill="currentColor"/></marker></defs>
<g font-family="inherit"><text x="150" y="48" fill="currentColor" font-size="13" text-anchor="end" font-family="inherit">book 7</text><rect x="164" y="26" width="14" height="30" fill="currentColor" fill-opacity="0.65" stroke="currentColor" stroke-width="1"/><rect x="182.8" y="26" width="7" height="30" fill="none" stroke="currentColor" stroke-width="1" stroke-dasharray="2 2" opacity="0.5"/><rect x="194.8" y="26" width="286" height="30" fill="currentColor" fill-opacity="0.65" stroke="currentColor" stroke-width="1"/><rect x="485.46000000000004" y="26" width="7" height="30" fill="none" stroke="currentColor" stroke-width="1" stroke-dasharray="2 2" opacity="0.5"/><text x="614" y="47" fill="currentColor" font-size="12.5" font-family="inherit">SUM <tspan font-weight="600">6.51</tspan></text><text x="694" y="47" fill="#e03131" font-size="12.5" font-family="inherit">MIN <tspan font-weight="600">0.00</tspan></text><text x="150" y="94" fill="currentColor" font-size="13" text-anchor="end" font-family="inherit">book 18</text><rect x="164" y="72" width="7" height="30" fill="none" stroke="currentColor" stroke-width="1" stroke-dasharray="2 2" opacity="0.5"/><rect x="176" y="72" width="7" height="30" fill="none" stroke="currentColor" stroke-width="1" stroke-dasharray="2 2" opacity="0.5"/><rect x="188" y="72" width="253" height="30" fill="currentColor" fill-opacity="0.65" stroke="currentColor" stroke-width="1"/><rect x="445.54" y="72" width="99" height="30" fill="currentColor" fill-opacity="0.65" stroke="currentColor" stroke-width="1"/><text x="614" y="93" fill="currentColor" font-size="12.5" font-family="inherit">SUM <tspan font-weight="600">7.64</tspan></text><text x="694" y="93" fill="#e03131" font-size="12.5" font-family="inherit">MIN <tspan font-weight="600">0.00</tspan></text><text x="150" y="140" fill="currentColor" font-size="13" text-anchor="end" font-family="inherit">book 22</text><rect x="164" y="118" width="50" height="30" fill="currentColor" fill-opacity="0.65" stroke="currentColor" stroke-width="1"/><rect x="219.14" y="118" width="10" height="30" fill="currentColor" fill-opacity="0.65" stroke="currentColor" stroke-width="1"/><rect x="234.26" y="118" width="10" height="30" fill="currentColor" fill-opacity="0.65" stroke="currentColor" stroke-width="1"/><rect x="249.38" y="118" width="190" height="30" fill="currentColor" fill-opacity="0.65" stroke="currentColor" stroke-width="1"/><text x="614" y="139" fill="currentColor" font-size="12.5" font-family="inherit">SUM <tspan font-weight="600">5.67</tspan></text><text x="694" y="139" fill="currentColor" font-size="12.5" font-family="inherit">MIN <tspan font-weight="600">0.22</tspan></text><text x="164" y="176" fill="currentColor" font-size="12.5" opacity="0.85">book 7 is a dinner party. book 22 is a massacre. <tspan font-weight="600">SUM ranks the dinner party higher.</tspan></text><text x="164" y="16" fill="currentColor" font-size="11.5" opacity="0.6">crisis &#183; crimes &#183; marks &#183; violence</text></g>
</svg>
Book 7 is a dinner party. Odysseus arrives at the palace of Alcinous, is bathed, given clean clothes, fed and questioned politely. Nobody is accused, expelled or harmed. Zero on crimes, zero on violence, and both zeros are correct.

Book 22 is Odysseus killing every suitor in the hall.

**On SUM the dinner party outscores the massacre**, 6.51 against 5.67. And on victim-marks it outscores every tragedy in the corpus. It beats *Oedipus*. It beats the *Bacchae*. The slaughter comes seventh.

Nothing went wrong with the code, and that is the part worth slowing down for. `marks` is 44% the word `king`, which was not a lazy choice, because in Girard the king is a victim whose execution has been deferred. Put that word list in front of book 7 and everyone in the room is a king, addressing a king, or describing one. The word saturates the passage for reasons of setting.

> **The false positive is not the lexicon misfiring. It is the lexicon working exactly as written**, on a text where one stereotype is present at maximum density and the other three are absent.

Which decides what repairs exist. A misfire you fix by editing words. This you cannot, because deleting `king` would delete a real victim mark and break the instrument the other way. The problem is not in the word list, so it cannot be solved in the word list.

Look at the MIN column. Book 7 scores **0.00**, correctly, on the only metric that encodes the claim.

## The trap, planted and not sprung

MIN has a property nobody considered, and it is arithmetic rather than literary. No amount of thinking harder about Girard would have surfaced it.

Two facts, side by side.

**MIN takes the smallest of four buckets.** And **`crimes` fires at 0.95 per thousand words, five times rarer than violence.**

You now have everything you need to see what is coming.

[[The Arithmetic All of It|Post 7]] takes it apart in one line of arithmetic that has nothing to do with Girard at all.
