---
title: The Arithmetic, All of It
---

*Part 7 of eleven. The series is [[Something That Can Say No]].*

Everything statistical in this project fits in one post. There are six ideas and none of them is hard.

That is worth saying plainly, because the failures ahead are not failures of sophistication. Nobody needed a better technique. Every one of them is a misuse of something on this list, made by somebody who could have explained the thing correctly if asked.

## 1. The median, not the mean

Every tier comparison here reports medians.

The reason is a single text.

`orphic_hymns_2` is a set of hymns. It is stuffed with the words *blameless* and *defend*, used as epithets in prayers. And it scores the corpus maximum on a lexicon built to find dissenting voices at a lynching. A false positive of the purest kind.

A mean lets that one text pull a whole tier. A median does not notice it exists.

The cost is that a median throws away magnitude. Two tiers can differ by a lot and be reported as differing by a little. You buy robustness with resolution, every time, and it is never free.

## 2. What a p-value actually is

Most people carry the wrong definition, so start by discarding it. A p-value is not the probability that your hypothesis is true. It is not the probability that the result is a fluke.

It is one thing only: **how surprised a world with nothing going on should be to have produced what you saw.**

Build one with no formula, using round 2.

| step | what you do | round 2's number |
|---|---|---|
| 1 | measure the real thing | separation of **6.10** |
| 2 | build one fake world where nothing is going on | 66 random frequency-matched words |
| 3 | do that two thousand times | fakes centre on **−0.16**, spread **2.95** |
| 4 | count how many fakes beat the real one | **8 of 2000** |

$$ p = \frac{\text{fakes at least as extreme} + 1}{\text{fakes} + 1} $$

Eight of two thousand is p = 0.0045. That is the whole apparatus.

<svg viewBox="0 0 760 210" width="100%" style="max-width:760px;height:auto;display:block;margin:2rem auto" role="img" aria-label="The null distribution as a histogram centred near zero with a spread of 2.95. The observed separation of 6.10 sits far out in the right tail, beaten by only eight of two thousand fake draws.">
<defs><marker id="a71" markerWidth="9" markerHeight="9" refX="8" refY="3" orient="auto"><path d="M0,0 L8,3 L0,6 z" fill="currentColor"/></marker></defs>
<rect x="70" y="144" width="23" height="2" fill="currentColor" fill-opacity="0.28" stroke="currentColor" stroke-width="0.8"/><rect x="96" y="143" width="23" height="3" fill="currentColor" fill-opacity="0.28" stroke="currentColor" stroke-width="0.8"/><rect x="122" y="138" width="23" height="8" fill="currentColor" fill-opacity="0.28" stroke="currentColor" stroke-width="0.8"/><rect x="148" y="129" width="23" height="17" fill="currentColor" fill-opacity="0.28" stroke="currentColor" stroke-width="0.8"/><rect x="174" y="116" width="23" height="30" fill="currentColor" fill-opacity="0.28" stroke="currentColor" stroke-width="0.8"/><rect x="200" y="96" width="23" height="50" fill="currentColor" fill-opacity="0.28" stroke="currentColor" stroke-width="0.8"/><rect x="226" y="73" width="23" height="73" fill="currentColor" fill-opacity="0.28" stroke="currentColor" stroke-width="0.8"/><rect x="252" y="52" width="23" height="94" fill="currentColor" fill-opacity="0.28" stroke="currentColor" stroke-width="0.8"/><rect x="278" y="37" width="23" height="109" fill="currentColor" fill-opacity="0.28" stroke="currentColor" stroke-width="0.8"/><rect x="304" y="34" width="23" height="112" fill="currentColor" fill-opacity="0.28" stroke="currentColor" stroke-width="0.8"/><rect x="330" y="46" width="23" height="100" fill="currentColor" fill-opacity="0.28" stroke="currentColor" stroke-width="0.8"/><rect x="356" y="67" width="23" height="79" fill="currentColor" fill-opacity="0.28" stroke="currentColor" stroke-width="0.8"/><rect x="382" y="90" width="23" height="56" fill="currentColor" fill-opacity="0.28" stroke="currentColor" stroke-width="0.8"/><rect x="408" y="110" width="23" height="36" fill="currentColor" fill-opacity="0.28" stroke="currentColor" stroke-width="0.8"/><rect x="434" y="125" width="23" height="21" fill="currentColor" fill-opacity="0.28" stroke="currentColor" stroke-width="0.8"/><rect x="460" y="135" width="23" height="11" fill="currentColor" fill-opacity="0.28" stroke="currentColor" stroke-width="0.8"/><rect x="486" y="140" width="23" height="6" fill="currentColor" fill-opacity="0.28" stroke="currentColor" stroke-width="0.8"/><rect x="512" y="143" width="23" height="3" fill="currentColor" fill-opacity="0.28" stroke="currentColor" stroke-width="0.8"/><rect x="538" y="144" width="23" height="2" fill="currentColor" fill-opacity="0.28" stroke="currentColor" stroke-width="0.8"/><rect x="564" y="144" width="23" height="2" fill="currentColor" fill-opacity="0.28" stroke="currentColor" stroke-width="0.8"/>
 <line x1="612" y1="30" x2="612" y2="146" stroke="#e03131" stroke-width="2.4"/>
 <text x="612" y="24" fill="#e03131" font-size="13" text-anchor="middle" font-family="inherit" font-weight="600">observed 6.10</text>
 <line x1="70" y1="146" x2="600" y2="146" stroke="currentColor" stroke-width="1.2"/>
 <text x="330" y="166" fill="currentColor" font-size="12.5" text-anchor="middle" font-family="inherit" opacity="0.85">2,000 fake worlds where nothing is going on</text>
 <text x="330" y="184" fill="currentColor" font-size="12" text-anchor="middle" font-family="inherit" opacity="0.65">centred on &#8722;0.16, spread 2.95</text>
 <text x="646" y="120" fill="#e03131" font-size="12.5" font-family="inherit" font-weight="600">8 of 2000</text>
 <text x="646" y="138" fill="#e03131" font-size="12.5" font-family="inherit" font-weight="600">beat it</text>
 <text x="646" y="160" fill="#e03131" font-size="12.5" font-family="inherit">p = 0.0045</text>
</svg>
The plus-one in the formula is not decoration. Without it, a result that no fake beat would report p = 0, which claims a certainty two thousand draws cannot support.

Your friend says he can tell Coke from Pepsi. You pour ten unmarked glasses and he gets nine right. The p-value asks how often a guesser gets nine of ten, and the answer is about one time in a hundred.

Notice what the test cannot do. It cannot tell you he is a supertaster rather than lucky, or that he peeked, or that your glasses were different shapes. It answers one narrow question about coin flips and says nothing about him.

**z** is the same information in different clothes. How many typical wobbles from nothing you are sitting. Zero means you look exactly like nothing happening.

$$ z = \frac{\text{observed} - \text{mean of the fakes}}{\text{sd of the fakes}} $$

## 3. Where 0.05 comes from, and it is not from mathematics

Every prediction in this project is judged against p < 0.05, and the number appears so often it starts to feel like a law.

**Ronald Fisher**, in a textbook in 1925, remarked that one in twenty was a convenient line for deciding whether a result was worth a second look. He was describing a rule of thumb for his own work. He later wrote against using any fixed level at all.

> **There is nothing behind 0.05 except that it is a round fraction and somebody influential said it out loud.**

Two things follow.

**p = 0.049 and p = 0.051 are the same result.** They differ by nothing. Treating one as a finding and the other as a failure is an artifact of a line drawn in 1925. Which is why this project prints the actual p-value everywhere instead of the word *significant*.

**And a threshold only means anything if you fix it before you look.** Arbitrary is fine. Arbitrary and chosen afterwards is not, because at that point you are picking the line that puts your result on the correct side of it.

## 4. One-sided, everywhere, and the bill it comes with

There is a fork in every p-value almost nobody says out loud, and it changes every number in this series by a factor of two.

| | the question | a huge effect the wrong way |
|---|---|---|
| two-sided | is there a difference | **counts** |
| **one-sided** | is it bigger, in the direction I named in advance | **returns nothing** |

Every prediction here is directional. Tragedy above control. Gospel above myth. Dissent nearer the violence. So every p-value in every round is one-sided.

> **A one-sided p-value is exactly half its two-sided equivalent on the same data.** Anybody who recomputes these the ordinary way gets figures twice as large, and the pre-registrations do not say which they used.

Say that before a commenter does. These particular results survive doubling, which is the only reason it is safe to state plainly, and that is a fact about these numbers rather than a defence of the practice.

<svg viewBox="0 0 760 180" width="100%" style="max-width:760px;height:auto;display:block;margin:2rem auto" role="img" aria-label="The same null distribution twice. The two-sided test counts surprises in both tails; the one-sided test counts only the tail it predicted, and returns exactly half the p-value.">
<defs><marker id="a72" markerWidth="9" markerHeight="9" refX="8" refY="3" orient="auto"><path d="M0,0 L8,3 L0,6 z" fill="currentColor"/></marker></defs>
<rect x="40" y="101" width="13" height="1" fill="currentColor" fill-opacity="0.62" stroke="currentColor" stroke-width="0.6"/><rect x="55" y="100" width="13" height="2" fill="currentColor" fill-opacity="0.62" stroke="currentColor" stroke-width="0.6"/><rect x="70" y="97" width="13" height="5" fill="currentColor" fill-opacity="0.62" stroke="currentColor" stroke-width="0.6"/><rect x="85" y="92" width="13" height="10" fill="currentColor" fill-opacity="0.62" stroke="currentColor" stroke-width="0.6"/><rect x="100" y="83" width="13" height="19" fill="currentColor" fill-opacity="0.62" stroke="currentColor" stroke-width="0.6"/><rect x="115" y="71" width="13" height="31" fill="currentColor" fill-opacity="0.62" stroke="currentColor" stroke-width="0.6"/><rect x="130" y="57" width="13" height="45" fill="currentColor" fill-opacity="0.62" stroke="currentColor" stroke-width="0.6"/><rect x="145" y="43" width="13" height="59" fill="currentColor" fill-opacity="0.16" stroke="currentColor" stroke-width="0.6"/><rect x="160" y="34" width="13" height="68" fill="currentColor" fill-opacity="0.16" stroke="currentColor" stroke-width="0.6"/><rect x="175" y="32" width="13" height="70" fill="currentColor" fill-opacity="0.16" stroke="currentColor" stroke-width="0.6"/><rect x="190" y="40" width="13" height="62" fill="currentColor" fill-opacity="0.16" stroke="currentColor" stroke-width="0.6"/><rect x="205" y="53" width="13" height="49" fill="currentColor" fill-opacity="0.16" stroke="currentColor" stroke-width="0.6"/><rect x="220" y="67" width="13" height="35" fill="currentColor" fill-opacity="0.16" stroke="currentColor" stroke-width="0.6"/><rect x="235" y="79" width="13" height="23" fill="currentColor" fill-opacity="0.62" stroke="currentColor" stroke-width="0.6"/><rect x="250" y="89" width="13" height="13" fill="currentColor" fill-opacity="0.62" stroke="currentColor" stroke-width="0.6"/><rect x="265" y="95" width="13" height="7" fill="currentColor" fill-opacity="0.62" stroke="currentColor" stroke-width="0.6"/><rect x="280" y="98" width="13" height="4" fill="currentColor" fill-opacity="0.62" stroke="currentColor" stroke-width="0.6"/><rect x="295" y="100" width="13" height="2" fill="currentColor" fill-opacity="0.62" stroke="currentColor" stroke-width="0.6"/><rect x="310" y="101" width="13" height="1" fill="currentColor" fill-opacity="0.62" stroke="currentColor" stroke-width="0.6"/><rect x="325" y="101" width="13" height="1" fill="currentColor" fill-opacity="0.62" stroke="currentColor" stroke-width="0.6"/><line x1="40" y1="102" x2="340" y2="102" stroke="currentColor" stroke-width="1.1"/><rect x="420" y="101" width="13" height="1" fill="currentColor" fill-opacity="0.16" stroke="currentColor" stroke-width="0.6"/><rect x="435" y="100" width="13" height="2" fill="currentColor" fill-opacity="0.16" stroke="currentColor" stroke-width="0.6"/><rect x="450" y="97" width="13" height="5" fill="currentColor" fill-opacity="0.16" stroke="currentColor" stroke-width="0.6"/><rect x="465" y="92" width="13" height="10" fill="currentColor" fill-opacity="0.16" stroke="currentColor" stroke-width="0.6"/><rect x="480" y="83" width="13" height="19" fill="currentColor" fill-opacity="0.16" stroke="currentColor" stroke-width="0.6"/><rect x="495" y="71" width="13" height="31" fill="currentColor" fill-opacity="0.16" stroke="currentColor" stroke-width="0.6"/><rect x="510" y="57" width="13" height="45" fill="currentColor" fill-opacity="0.16" stroke="currentColor" stroke-width="0.6"/><rect x="525" y="43" width="13" height="59" fill="currentColor" fill-opacity="0.16" stroke="currentColor" stroke-width="0.6"/><rect x="540" y="34" width="13" height="68" fill="currentColor" fill-opacity="0.16" stroke="currentColor" stroke-width="0.6"/><rect x="555" y="32" width="13" height="70" fill="currentColor" fill-opacity="0.16" stroke="currentColor" stroke-width="0.6"/><rect x="570" y="40" width="13" height="62" fill="currentColor" fill-opacity="0.16" stroke="currentColor" stroke-width="0.6"/><rect x="585" y="53" width="13" height="49" fill="currentColor" fill-opacity="0.16" stroke="currentColor" stroke-width="0.6"/><rect x="600" y="67" width="13" height="35" fill="currentColor" fill-opacity="0.16" stroke="currentColor" stroke-width="0.6"/><rect x="615" y="79" width="13" height="23" fill="currentColor" fill-opacity="0.62" stroke="currentColor" stroke-width="0.6"/><rect x="630" y="89" width="13" height="13" fill="currentColor" fill-opacity="0.62" stroke="currentColor" stroke-width="0.6"/><rect x="645" y="95" width="13" height="7" fill="currentColor" fill-opacity="0.62" stroke="currentColor" stroke-width="0.6"/><rect x="660" y="98" width="13" height="4" fill="currentColor" fill-opacity="0.62" stroke="currentColor" stroke-width="0.6"/><rect x="675" y="100" width="13" height="2" fill="currentColor" fill-opacity="0.62" stroke="currentColor" stroke-width="0.6"/><rect x="690" y="101" width="13" height="1" fill="currentColor" fill-opacity="0.62" stroke="currentColor" stroke-width="0.6"/><rect x="705" y="101" width="13" height="1" fill="currentColor" fill-opacity="0.62" stroke="currentColor" stroke-width="0.6"/><line x1="420" y1="102" x2="720" y2="102" stroke="currentColor" stroke-width="1.1"/>
 <g fill="currentColor" font-family="inherit" text-anchor="middle">
  <text x="190" y="28" font-size="13" font-weight="600">two-sided</text>
  <text x="570" y="28" font-size="13" font-weight="600">one-sided</text>
  <text x="190" y="128" font-size="12.5" opacity="0.85">counts a surprise either way</text>
  <text x="570" y="128" font-size="12.5" opacity="0.85">counts only the direction you named first</text>
  <text x="190" y="152" font-size="13" font-weight="600">p = 0.00068</text>
  <text x="570" y="152" font-size="13" font-weight="600">p = 0.00034</text>
  <text x="380" y="174" font-size="12" opacity="0.7">every p-value in this project is the right-hand one. double them and they survive.</text>
 </g>
</svg>
And the cost is real, which is why the direction has to be fixed in advance. **You buy sensitivity by agreeing not to notice being wrong backwards.**

[[Ten Rounds and the Half That Never Carried Anything|Post 9]] contains a result that runs backwards. In one half of the instrument, tragedy climbs above the Gospels. No test in that round is capable of registering it as a result, because every test was pointed the other way.

## 5. Mann-Whitney U, which is simpler than its name

Four Gospel scores. Seventy-one myth scores. Line all seventy-five up and ask one question: how often does a Gospel text beat a myth text?

Compare every Gospel against every myth, one pair at a time, and count the wins. That count is U.

| | |
|---|---|
| every possible pair | 4 × 71 = **284** |
| Gospels win all of them | U = 284 |
| evenly matched | U = **142** |
| **observed** | **U = 268** |

> **U = 268 means the Gospels won 268 of 284 head-to-head comparisons.** No formula, no assumption about the shape of the data, just counting who beat whom.

It is used instead of comparing averages because **it does not care how big the wins are.** One wild text cannot drag the result. Which matters in a corpus where `orphic_hymns_2` exists.

## 6. Rare things clump, and this is where the instrument broke

Do this before any formula.

A cake cut into a hundred slices with a hundred raisins mixed through it. How many raisins in the average slice? One.

How many slices have no raisin at all?

**Thirty-seven.**

Raisins do not queue up politely. Some slices get three, some get two, and more than a third get zero even though the average is one.

<svg viewBox="0 0 760 292" width="100%" style="max-width:760px;height:auto;display:block;margin:2rem auto" role="img" aria-label="A cake of a hundred slices with a hundred raisins scattered through it. The average slice holds one raisin, and 38 slices hold none at all.">
<defs><marker id="a73" markerWidth="9" markerHeight="9" refX="8" refY="3" orient="auto"><path d="M0,0 L8,3 L0,6 z" fill="currentColor"/></marker></defs>
<rect x="180" y="26" width="31" height="19" fill="currentColor" fill-opacity="0.0" stroke="currentColor" stroke-width="0.7" opacity="0.45"/><rect x="214" y="26" width="31" height="19" fill="currentColor" fill-opacity="0.0" stroke="currentColor" stroke-width="0.7" opacity="0.45"/><rect x="248" y="26" width="31" height="19" fill="currentColor" fill-opacity="0.0" stroke="currentColor" stroke-width="0.7" opacity="0.45"/><rect x="282" y="26" width="31" height="19" fill="currentColor" fill-opacity="0.0" stroke="currentColor" stroke-width="0.7" opacity="0.45"/><rect x="316" y="26" width="31" height="19" fill="currentColor" fill-opacity="0.3" stroke="currentColor" stroke-width="0.7" opacity="1"/><text x="331.5" y="40" fill="currentColor" font-size="11" text-anchor="middle" font-family="inherit">1</text><rect x="350" y="26" width="31" height="19" fill="currentColor" fill-opacity="0.62" stroke="currentColor" stroke-width="0.7" opacity="1"/><text x="365.5" y="40" fill="currentColor" font-size="11" text-anchor="middle" font-family="inherit">2</text><rect x="384" y="26" width="31" height="19" fill="currentColor" fill-opacity="0.62" stroke="currentColor" stroke-width="0.7" opacity="1"/><text x="399.5" y="40" fill="currentColor" font-size="11" text-anchor="middle" font-family="inherit">2</text><rect x="418" y="26" width="31" height="19" fill="currentColor" fill-opacity="0.62" stroke="currentColor" stroke-width="0.7" opacity="1"/><text x="433.5" y="40" fill="currentColor" font-size="11" text-anchor="middle" font-family="inherit">4</text><rect x="452" y="26" width="31" height="19" fill="currentColor" fill-opacity="0.62" stroke="currentColor" stroke-width="0.7" opacity="1"/><text x="467.5" y="40" fill="currentColor" font-size="11" text-anchor="middle" font-family="inherit">2</text><rect x="486" y="26" width="31" height="19" fill="currentColor" fill-opacity="0.62" stroke="currentColor" stroke-width="0.7" opacity="1"/><text x="501.5" y="40" fill="currentColor" font-size="11" text-anchor="middle" font-family="inherit">2</text><rect x="180" y="48" width="31" height="19" fill="currentColor" fill-opacity="0.3" stroke="currentColor" stroke-width="0.7" opacity="1"/><text x="195.5" y="62" fill="currentColor" font-size="11" text-anchor="middle" font-family="inherit">1</text><rect x="214" y="48" width="31" height="19" fill="currentColor" fill-opacity="0.62" stroke="currentColor" stroke-width="0.7" opacity="1"/><text x="229.5" y="62" fill="currentColor" font-size="11" text-anchor="middle" font-family="inherit">2</text><rect x="248" y="48" width="31" height="19" fill="currentColor" fill-opacity="0.62" stroke="currentColor" stroke-width="0.7" opacity="1"/><text x="263.5" y="62" fill="currentColor" font-size="11" text-anchor="middle" font-family="inherit">2</text><rect x="282" y="48" width="31" height="19" fill="currentColor" fill-opacity="0.3" stroke="currentColor" stroke-width="0.7" opacity="1"/><text x="297.5" y="62" fill="currentColor" font-size="11" text-anchor="middle" font-family="inherit">1</text><rect x="316" y="48" width="31" height="19" fill="currentColor" fill-opacity="0.0" stroke="currentColor" stroke-width="0.7" opacity="0.45"/><rect x="350" y="48" width="31" height="19" fill="currentColor" fill-opacity="0.62" stroke="currentColor" stroke-width="0.7" opacity="1"/><text x="365.5" y="62" fill="currentColor" font-size="11" text-anchor="middle" font-family="inherit">3</text><rect x="384" y="48" width="31" height="19" fill="currentColor" fill-opacity="0.0" stroke="currentColor" stroke-width="0.7" opacity="0.45"/><rect x="418" y="48" width="31" height="19" fill="currentColor" fill-opacity="0.3" stroke="currentColor" stroke-width="0.7" opacity="1"/><text x="433.5" y="62" fill="currentColor" font-size="11" text-anchor="middle" font-family="inherit">1</text><rect x="452" y="48" width="31" height="19" fill="currentColor" fill-opacity="0.3" stroke="currentColor" stroke-width="0.7" opacity="1"/><text x="467.5" y="62" fill="currentColor" font-size="11" text-anchor="middle" font-family="inherit">1</text><rect x="486" y="48" width="31" height="19" fill="currentColor" fill-opacity="0.62" stroke="currentColor" stroke-width="0.7" opacity="1"/><text x="501.5" y="62" fill="currentColor" font-size="11" text-anchor="middle" font-family="inherit">2</text><rect x="180" y="70" width="31" height="19" fill="currentColor" fill-opacity="0.0" stroke="currentColor" stroke-width="0.7" opacity="0.45"/><rect x="214" y="70" width="31" height="19" fill="currentColor" fill-opacity="0.3" stroke="currentColor" stroke-width="0.7" opacity="1"/><text x="229.5" y="84" fill="currentColor" font-size="11" text-anchor="middle" font-family="inherit">1</text><rect x="248" y="70" width="31" height="19" fill="currentColor" fill-opacity="0.0" stroke="currentColor" stroke-width="0.7" opacity="0.45"/><rect x="282" y="70" width="31" height="19" fill="currentColor" fill-opacity="0.62" stroke="currentColor" stroke-width="0.7" opacity="1"/><text x="297.5" y="84" fill="currentColor" font-size="11" text-anchor="middle" font-family="inherit">2</text><rect x="316" y="70" width="31" height="19" fill="currentColor" fill-opacity="0.3" stroke="currentColor" stroke-width="0.7" opacity="1"/><text x="331.5" y="84" fill="currentColor" font-size="11" text-anchor="middle" font-family="inherit">1</text><rect x="350" y="70" width="31" height="19" fill="currentColor" fill-opacity="0.0" stroke="currentColor" stroke-width="0.7" opacity="0.45"/><rect x="384" y="70" width="31" height="19" fill="currentColor" fill-opacity="0.3" stroke="currentColor" stroke-width="0.7" opacity="1"/><text x="399.5" y="84" fill="currentColor" font-size="11" text-anchor="middle" font-family="inherit">1</text><rect x="418" y="70" width="31" height="19" fill="currentColor" fill-opacity="0.3" stroke="currentColor" stroke-width="0.7" opacity="1"/><text x="433.5" y="84" fill="currentColor" font-size="11" text-anchor="middle" font-family="inherit">1</text><rect x="452" y="70" width="31" height="19" fill="currentColor" fill-opacity="0.62" stroke="currentColor" stroke-width="0.7" opacity="1"/><text x="467.5" y="84" fill="currentColor" font-size="11" text-anchor="middle" font-family="inherit">2</text><rect x="486" y="70" width="31" height="19" fill="currentColor" fill-opacity="0.0" stroke="currentColor" stroke-width="0.7" opacity="0.45"/><rect x="180" y="92" width="31" height="19" fill="currentColor" fill-opacity="0.3" stroke="currentColor" stroke-width="0.7" opacity="1"/><text x="195.5" y="106" fill="currentColor" font-size="11" text-anchor="middle" font-family="inherit">1</text><rect x="214" y="92" width="31" height="19" fill="currentColor" fill-opacity="0.62" stroke="currentColor" stroke-width="0.7" opacity="1"/><text x="229.5" y="106" fill="currentColor" font-size="11" text-anchor="middle" font-family="inherit">2</text><rect x="248" y="92" width="31" height="19" fill="currentColor" fill-opacity="0.0" stroke="currentColor" stroke-width="0.7" opacity="0.45"/><rect x="282" y="92" width="31" height="19" fill="currentColor" fill-opacity="0.0" stroke="currentColor" stroke-width="0.7" opacity="0.45"/><rect x="316" y="92" width="31" height="19" fill="currentColor" fill-opacity="0.0" stroke="currentColor" stroke-width="0.7" opacity="0.45"/><rect x="350" y="92" width="31" height="19" fill="currentColor" fill-opacity="0.0" stroke="currentColor" stroke-width="0.7" opacity="0.45"/><rect x="384" y="92" width="31" height="19" fill="currentColor" fill-opacity="0.3" stroke="currentColor" stroke-width="0.7" opacity="1"/><text x="399.5" y="106" fill="currentColor" font-size="11" text-anchor="middle" font-family="inherit">1</text><rect x="418" y="92" width="31" height="19" fill="currentColor" fill-opacity="0.3" stroke="currentColor" stroke-width="0.7" opacity="1"/><text x="433.5" y="106" fill="currentColor" font-size="11" text-anchor="middle" font-family="inherit">1</text><rect x="452" y="92" width="31" height="19" fill="currentColor" fill-opacity="0.62" stroke="currentColor" stroke-width="0.7" opacity="1"/><text x="467.5" y="106" fill="currentColor" font-size="11" text-anchor="middle" font-family="inherit">2</text><rect x="486" y="92" width="31" height="19" fill="currentColor" fill-opacity="0.3" stroke="currentColor" stroke-width="0.7" opacity="1"/><text x="501.5" y="106" fill="currentColor" font-size="11" text-anchor="middle" font-family="inherit">1</text><rect x="180" y="114" width="31" height="19" fill="currentColor" fill-opacity="0.3" stroke="currentColor" stroke-width="0.7" opacity="1"/><text x="195.5" y="128" fill="currentColor" font-size="11" text-anchor="middle" font-family="inherit">1</text><rect x="214" y="114" width="31" height="19" fill="currentColor" fill-opacity="0.3" stroke="currentColor" stroke-width="0.7" opacity="1"/><text x="229.5" y="128" fill="currentColor" font-size="11" text-anchor="middle" font-family="inherit">1</text><rect x="248" y="114" width="31" height="19" fill="currentColor" fill-opacity="0.0" stroke="currentColor" stroke-width="0.7" opacity="0.45"/><rect x="282" y="114" width="31" height="19" fill="currentColor" fill-opacity="0.62" stroke="currentColor" stroke-width="0.7" opacity="1"/><text x="297.5" y="128" fill="currentColor" font-size="11" text-anchor="middle" font-family="inherit">2</text><rect x="316" y="114" width="31" height="19" fill="currentColor" fill-opacity="0.0" stroke="currentColor" stroke-width="0.7" opacity="0.45"/><rect x="350" y="114" width="31" height="19" fill="currentColor" fill-opacity="0.0" stroke="currentColor" stroke-width="0.7" opacity="0.45"/><rect x="384" y="114" width="31" height="19" fill="currentColor" fill-opacity="0.62" stroke="currentColor" stroke-width="0.7" opacity="1"/><text x="399.5" y="128" fill="currentColor" font-size="11" text-anchor="middle" font-family="inherit">2</text><rect x="418" y="114" width="31" height="19" fill="currentColor" fill-opacity="0.3" stroke="currentColor" stroke-width="0.7" opacity="1"/><text x="433.5" y="128" fill="currentColor" font-size="11" text-anchor="middle" font-family="inherit">1</text><rect x="452" y="114" width="31" height="19" fill="currentColor" fill-opacity="0.0" stroke="currentColor" stroke-width="0.7" opacity="0.45"/><rect x="486" y="114" width="31" height="19" fill="currentColor" fill-opacity="0.0" stroke="currentColor" stroke-width="0.7" opacity="0.45"/><rect x="180" y="136" width="31" height="19" fill="currentColor" fill-opacity="0.62" stroke="currentColor" stroke-width="0.7" opacity="1"/><text x="195.5" y="150" fill="currentColor" font-size="11" text-anchor="middle" font-family="inherit">2</text><rect x="214" y="136" width="31" height="19" fill="currentColor" fill-opacity="0.0" stroke="currentColor" stroke-width="0.7" opacity="0.45"/><rect x="248" y="136" width="31" height="19" fill="currentColor" fill-opacity="0.0" stroke="currentColor" stroke-width="0.7" opacity="0.45"/><rect x="282" y="136" width="31" height="19" fill="currentColor" fill-opacity="0.62" stroke="currentColor" stroke-width="0.7" opacity="1"/><text x="297.5" y="150" fill="currentColor" font-size="11" text-anchor="middle" font-family="inherit">4</text><rect x="316" y="136" width="31" height="19" fill="currentColor" fill-opacity="0.62" stroke="currentColor" stroke-width="0.7" opacity="1"/><text x="331.5" y="150" fill="currentColor" font-size="11" text-anchor="middle" font-family="inherit">2</text><rect x="350" y="136" width="31" height="19" fill="currentColor" fill-opacity="0.3" stroke="currentColor" stroke-width="0.7" opacity="1"/><text x="365.5" y="150" fill="currentColor" font-size="11" text-anchor="middle" font-family="inherit">1</text><rect x="384" y="136" width="31" height="19" fill="currentColor" fill-opacity="0.0" stroke="currentColor" stroke-width="0.7" opacity="0.45"/><rect x="418" y="136" width="31" height="19" fill="currentColor" fill-opacity="0.3" stroke="currentColor" stroke-width="0.7" opacity="1"/><text x="433.5" y="150" fill="currentColor" font-size="11" text-anchor="middle" font-family="inherit">1</text><rect x="452" y="136" width="31" height="19" fill="currentColor" fill-opacity="0.3" stroke="currentColor" stroke-width="0.7" opacity="1"/><text x="467.5" y="150" fill="currentColor" font-size="11" text-anchor="middle" font-family="inherit">1</text><rect x="486" y="136" width="31" height="19" fill="currentColor" fill-opacity="0.3" stroke="currentColor" stroke-width="0.7" opacity="1"/><text x="501.5" y="150" fill="currentColor" font-size="11" text-anchor="middle" font-family="inherit">1</text><rect x="180" y="158" width="31" height="19" fill="currentColor" fill-opacity="0.0" stroke="currentColor" stroke-width="0.7" opacity="0.45"/><rect x="214" y="158" width="31" height="19" fill="currentColor" fill-opacity="0.0" stroke="currentColor" stroke-width="0.7" opacity="0.45"/><rect x="248" y="158" width="31" height="19" fill="currentColor" fill-opacity="0.3" stroke="currentColor" stroke-width="0.7" opacity="1"/><text x="263.5" y="172" fill="currentColor" font-size="11" text-anchor="middle" font-family="inherit">1</text><rect x="282" y="158" width="31" height="19" fill="currentColor" fill-opacity="0.62" stroke="currentColor" stroke-width="0.7" opacity="1"/><text x="297.5" y="172" fill="currentColor" font-size="11" text-anchor="middle" font-family="inherit">2</text><rect x="316" y="158" width="31" height="19" fill="currentColor" fill-opacity="0.3" stroke="currentColor" stroke-width="0.7" opacity="1"/><text x="331.5" y="172" fill="currentColor" font-size="11" text-anchor="middle" font-family="inherit">1</text><rect x="350" y="158" width="31" height="19" fill="currentColor" fill-opacity="0.3" stroke="currentColor" stroke-width="0.7" opacity="1"/><text x="365.5" y="172" fill="currentColor" font-size="11" text-anchor="middle" font-family="inherit">1</text><rect x="384" y="158" width="31" height="19" fill="currentColor" fill-opacity="0.0" stroke="currentColor" stroke-width="0.7" opacity="0.45"/><rect x="418" y="158" width="31" height="19" fill="currentColor" fill-opacity="0.3" stroke="currentColor" stroke-width="0.7" opacity="1"/><text x="433.5" y="172" fill="currentColor" font-size="11" text-anchor="middle" font-family="inherit">1</text><rect x="452" y="158" width="31" height="19" fill="currentColor" fill-opacity="0.62" stroke="currentColor" stroke-width="0.7" opacity="1"/><text x="467.5" y="172" fill="currentColor" font-size="11" text-anchor="middle" font-family="inherit">2</text><rect x="486" y="158" width="31" height="19" fill="currentColor" fill-opacity="0.3" stroke="currentColor" stroke-width="0.7" opacity="1"/><text x="501.5" y="172" fill="currentColor" font-size="11" text-anchor="middle" font-family="inherit">1</text><rect x="180" y="180" width="31" height="19" fill="currentColor" fill-opacity="0.62" stroke="currentColor" stroke-width="0.7" opacity="1"/><text x="195.5" y="194" fill="currentColor" font-size="11" text-anchor="middle" font-family="inherit">2</text><rect x="214" y="180" width="31" height="19" fill="currentColor" fill-opacity="0.62" stroke="currentColor" stroke-width="0.7" opacity="1"/><text x="229.5" y="194" fill="currentColor" font-size="11" text-anchor="middle" font-family="inherit">2</text><rect x="248" y="180" width="31" height="19" fill="currentColor" fill-opacity="0.62" stroke="currentColor" stroke-width="0.7" opacity="1"/><text x="263.5" y="194" fill="currentColor" font-size="11" text-anchor="middle" font-family="inherit">2</text><rect x="282" y="180" width="31" height="19" fill="currentColor" fill-opacity="0.62" stroke="currentColor" stroke-width="0.7" opacity="1"/><text x="297.5" y="194" fill="currentColor" font-size="11" text-anchor="middle" font-family="inherit">4</text><rect x="316" y="180" width="31" height="19" fill="currentColor" fill-opacity="0.62" stroke="currentColor" stroke-width="0.7" opacity="1"/><text x="331.5" y="194" fill="currentColor" font-size="11" text-anchor="middle" font-family="inherit">5</text><rect x="350" y="180" width="31" height="19" fill="currentColor" fill-opacity="0.0" stroke="currentColor" stroke-width="0.7" opacity="0.45"/><rect x="384" y="180" width="31" height="19" fill="currentColor" fill-opacity="0.0" stroke="currentColor" stroke-width="0.7" opacity="0.45"/><rect x="418" y="180" width="31" height="19" fill="currentColor" fill-opacity="0.3" stroke="currentColor" stroke-width="0.7" opacity="1"/><text x="433.5" y="194" fill="currentColor" font-size="11" text-anchor="middle" font-family="inherit">1</text><rect x="452" y="180" width="31" height="19" fill="currentColor" fill-opacity="0.0" stroke="currentColor" stroke-width="0.7" opacity="0.45"/><rect x="486" y="180" width="31" height="19" fill="currentColor" fill-opacity="0.3" stroke="currentColor" stroke-width="0.7" opacity="1"/><text x="501.5" y="194" fill="currentColor" font-size="11" text-anchor="middle" font-family="inherit">1</text><rect x="180" y="202" width="31" height="19" fill="currentColor" fill-opacity="0.62" stroke="currentColor" stroke-width="0.7" opacity="1"/><text x="195.5" y="216" fill="currentColor" font-size="11" text-anchor="middle" font-family="inherit">2</text><rect x="214" y="202" width="31" height="19" fill="currentColor" fill-opacity="0.3" stroke="currentColor" stroke-width="0.7" opacity="1"/><text x="229.5" y="216" fill="currentColor" font-size="11" text-anchor="middle" font-family="inherit">1</text><rect x="248" y="202" width="31" height="19" fill="currentColor" fill-opacity="0.0" stroke="currentColor" stroke-width="0.7" opacity="0.45"/><rect x="282" y="202" width="31" height="19" fill="currentColor" fill-opacity="0.3" stroke="currentColor" stroke-width="0.7" opacity="1"/><text x="297.5" y="216" fill="currentColor" font-size="11" text-anchor="middle" font-family="inherit">1</text><rect x="316" y="202" width="31" height="19" fill="currentColor" fill-opacity="0.0" stroke="currentColor" stroke-width="0.7" opacity="0.45"/><rect x="350" y="202" width="31" height="19" fill="currentColor" fill-opacity="0.3" stroke="currentColor" stroke-width="0.7" opacity="1"/><text x="365.5" y="216" fill="currentColor" font-size="11" text-anchor="middle" font-family="inherit">1</text><rect x="384" y="202" width="31" height="19" fill="currentColor" fill-opacity="0.0" stroke="currentColor" stroke-width="0.7" opacity="0.45"/><rect x="418" y="202" width="31" height="19" fill="currentColor" fill-opacity="0.62" stroke="currentColor" stroke-width="0.7" opacity="1"/><text x="433.5" y="216" fill="currentColor" font-size="11" text-anchor="middle" font-family="inherit">2</text><rect x="452" y="202" width="31" height="19" fill="currentColor" fill-opacity="0.0" stroke="currentColor" stroke-width="0.7" opacity="0.45"/><rect x="486" y="202" width="31" height="19" fill="currentColor" fill-opacity="0.3" stroke="currentColor" stroke-width="0.7" opacity="1"/><text x="501.5" y="216" fill="currentColor" font-size="11" text-anchor="middle" font-family="inherit">1</text><rect x="180" y="224" width="31" height="19" fill="currentColor" fill-opacity="0.0" stroke="currentColor" stroke-width="0.7" opacity="0.45"/><rect x="214" y="224" width="31" height="19" fill="currentColor" fill-opacity="0.3" stroke="currentColor" stroke-width="0.7" opacity="1"/><text x="229.5" y="238" fill="currentColor" font-size="11" text-anchor="middle" font-family="inherit">1</text><rect x="248" y="224" width="31" height="19" fill="currentColor" fill-opacity="0.0" stroke="currentColor" stroke-width="0.7" opacity="0.45"/><rect x="282" y="224" width="31" height="19" fill="currentColor" fill-opacity="0.3" stroke="currentColor" stroke-width="0.7" opacity="1"/><text x="297.5" y="238" fill="currentColor" font-size="11" text-anchor="middle" font-family="inherit">1</text><rect x="316" y="224" width="31" height="19" fill="currentColor" fill-opacity="0.0" stroke="currentColor" stroke-width="0.7" opacity="0.45"/><rect x="350" y="224" width="31" height="19" fill="currentColor" fill-opacity="0.0" stroke="currentColor" stroke-width="0.7" opacity="0.45"/><rect x="384" y="224" width="31" height="19" fill="currentColor" fill-opacity="0.3" stroke="currentColor" stroke-width="0.7" opacity="1"/><text x="399.5" y="238" fill="currentColor" font-size="11" text-anchor="middle" font-family="inherit">1</text><rect x="418" y="224" width="31" height="19" fill="currentColor" fill-opacity="0.0" stroke="currentColor" stroke-width="0.7" opacity="0.45"/><rect x="452" y="224" width="31" height="19" fill="currentColor" fill-opacity="0.0" stroke="currentColor" stroke-width="0.7" opacity="0.45"/><rect x="486" y="224" width="31" height="19" fill="currentColor" fill-opacity="0.62" stroke="currentColor" stroke-width="0.7" opacity="1"/><text x="501.5" y="238" fill="currentColor" font-size="11" text-anchor="middle" font-family="inherit">2</text>
 <text x="345" y="18" fill="currentColor" font-size="12.5" text-anchor="middle" font-family="inherit" opacity="0.8">100 raisins, 100 slices. average per slice: 1.</text>
 <text x="558" y="128" fill="#e03131" font-size="34" font-family="inherit" font-weight="600">38</text>
 <text x="558" y="150" fill="#e03131" font-size="12.5" font-family="inherit" font-weight="600">slices hold none</text>
 <text x="558" y="172" fill="currentColor" font-size="12.5" font-family="inherit" opacity="0.8">even though the average is one</text>
 <text x="345" y="272" fill="currentColor" font-size="13" text-anchor="middle" font-family="inherit">e<tspan font-size="10" dy="-6">&#8722;1</tspan><tspan dy="6"> = 0.37. the formula only names the cake.</tspan></text>
</svg>
Everyone already knows this from somewhere else. A hundred gacha pulls at 1% and nothing, which is not a lie and not rigged. Coming away empty is the ordinary outcome, and the pity counter exists because of this arithmetic.

For a bucket firing at rate λ per thousand words, over N words, the expected count is λN/1000. The chance of seeing none at all is e raised to minus that.

The formula is the cake.

Now the corpus numbers, measured across 76 texts.

| bucket | rate per 1000 |
|---|---|
| violence | 4.76 |
| marks | 2.90 |
| crisis | 2.07 |
| **crimes** | **0.95** |

`crimes` is the rare one, and it is rare for a reason rather than by accident. The crime stereotype is the one Girard names with **nouns**, parricide and regicide and sacrilege, and Greek literature describes those events with verbs. The thin bucket is thin because it was built out of the vocabulary of verdicts.

Put it through the cake.

| text length | expected `crimes` hits | P(zero) |
|---|---|---|
| **1,500 words**, one Ovid myth | 1.42 | **0.24** |
| 10,000 words, a tragedy | 9.49 | ~0.000 |
| 17,180 words, the *Bacchae* | 16.31 | ~0.000 |

Read the gap between the first row and the second, because it is the whole thing. At tragedy length the bucket essentially never comes up empty. At Ovid length it is empty a quarter of the time.

Same instrument, same lexicon, same corpus. **Only the length changed, and the instrument silently became a different instrument.**

And those are the optimistic numbers. They are computed on the repaired lexicon. The original caught `murder` 138 times out of 297 real occurrences, so its effective rate was lower and its zero probability higher.

## What that does to MIN

[[Turning Four Sentences Into Code|Post 4]] planted this and here is the detonation.

**MIN takes the weakest bucket.** If the weakest bucket is zero for a quarter of your texts, MIN is zero for a quarter of your texts.

A statistic that is zero a quarter of the time carries almost no information.

A quarter of the corpus sits pinned at the same value regardless of anything else in it. So a high-scoring text and a low-scoring text that both hit an empty `crimes` bucket are indistinguishable. Not because they resemble each other. Because the statistic ran out of room underneath them.

> **The minimum did not fail because Girard is wrong. It failed because you cannot take the minimum of something that is usually absent.**

[[Turning Four Sentences Into Code|Post 4]] chose MIN for entirely correct theoretical reasons. The reasoning was right. The arithmetic was never checked.

Those are two separate competences and I had one of them. Which is the ordinary condition of anybody building an instrument out of a theory they understand better than they understand the statistic.

## 7. Power, and the falsifier that exists because of round 3

Round 3's statistic was the minimum of four counts inside a 1,000-word window.

| | |
|---|---|
| observed range | **0 to 5** |
| median | **2** |
| texts where the weakest bucket contributes 3 or fewer | **64 of 71** |

> **This is a statistic built on counting to two.**

Five predictions, seventy-one texts, two nulls and two thousand permutations all rest on whether a number that is usually two is bigger than another number that is usually two.

**Power is the probability that your test finds an effect that is really there.** When power is low, a null result cannot distinguish between two completely different situations. There is no effect. Or there is one, and your instrument could never have seen it.

Weighing a letter on a bathroom scale. The letter has a weight. The scale is not broken. You still learn nothing, and the reading tells you about the scale rather than about the letter.

<svg viewBox="0 0 760 216" width="100%" style="max-width:760px;height:auto;display:block;margin:2rem auto" role="img" aria-label="The same letter on a bathroom scale reading zero and on kitchen scales reading twenty-four grams. The zero is a fact about the scale, not about the letter.">
<defs><marker id="a74" markerWidth="9" markerHeight="9" refX="8" refY="3" orient="auto"><path d="M0,0 L8,3 L0,6 z" fill="currentColor"/></marker></defs>
<g fill="none" stroke="currentColor" stroke-width="1.6">
  <rect x="90" y="60" width="200" height="96" rx="8"/><rect x="470" y="60" width="200" height="96" rx="8"/>
 </g>
 <rect x="150" y="34" width="80" height="26" fill="currentColor" fill-opacity="0.15" stroke="currentColor" stroke-width="1.2"/>
 <rect x="530" y="34" width="80" height="26" fill="currentColor" fill-opacity="0.15" stroke="currentColor" stroke-width="1.2"/>
 <g fill="currentColor" font-family="inherit" text-anchor="middle">
  <text x="190" y="52" font-size="11.5" opacity="0.7">the letter</text>
  <text x="570" y="52" font-size="11.5" opacity="0.7">the letter</text>
  <text x="190" y="122" font-size="38" font-weight="600" fill="#e03131">0</text>
  <text x="570" y="122" font-size="38" font-weight="600">24g</text>
  <text x="190" y="146" font-size="12" opacity="0.7">kg</text><text x="570" y="146" font-size="12" opacity="0.7">grams</text>
  <text x="190" y="180" font-size="13" font-weight="600">bathroom scale</text>
  <text x="570" y="180" font-size="13" font-weight="600">kitchen scales</text>
  <text x="380" y="206" font-size="12.5" opacity="0.85">the letter has a weight either way. <tspan font-weight="600">the zero is a fact about the scale.</tspan></text>
 </g>
</svg>
Round 3's own results file says it plainly, and this is the sentence the project should be judged on rather than its p-values:

> "The honest position is that the test as specified had little power, and that **this was foreseeable before running it and was not foreseen.**"

The fix was structural rather than clever.

Every round from that point carries a **power falsifier**. A number fixed in advance, saying *if the statistic comes out this flat, report the round as under-powered rather than as an absence*.

In round 7 it fired. Median z across 66 texts came out at **−0.012**, inside a band declared before anything ran, and the round was reported as unable to see rather than as having found nothing.

Round 3 could not make that distinction. Every round after it can, and the only reason is that somebody wrote a number down in advance instead of arguing about it afterwards.

## And one thing against myself

Make one prediction at a threshold of 0.05 and you accept a one in twenty chance of a false pass. Make thirty and you should expect about one and a half false passes **even if nothing is true anywhere.**

This project made roughly fifty committed predictions. It applied no correction for that, anywhere, in any round.

It matters less than it sounds, and it is worth working out why before [[Ten Rounds and the Half That Never Carried Anything|post 9]] says it. The hint is to think about what multiplicity inflates, and then to go and look at how many of this project's predictions actually passed.

[[What a Timestamp Actually Proves|Post 8]] is about the machinery that was supposed to make all of this trustworthy, and what it does and does not prove.
