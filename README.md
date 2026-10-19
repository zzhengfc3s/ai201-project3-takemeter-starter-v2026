# TakeMeter

> ### 👋 Start here
>
> **New to this repo? Read [RUNNING.md](RUNNING.md) first** — setup, the
> notebook, the baseline, and what to do when something breaks.
>
> Once `python test.py` passes:
>
> ```bash
> head -5 data/practice_labels.csv     # the shape your labels.csv needs
> ```
>
> Then open `takemeter.ipynb` **in this folder** — in VS Code, or with
> `jupyter notebook` if you prefer. Pick the kernel: the `.venv` inside this
> project. Run section 1, which reports the hardware you'll be training on.
> Everything else waits until you have data.
>
> Nothing to upload, nothing to connect, no accounts and no keys. The notebook
> runs on your machine and writes next to your code.
>
> **The rest of this file is your submission.** Fill it in as you go.

---

<!-- ─────────────────────────────────────────────────────────────────────────
     HOW TO USE THIS FILE

     Unit 5 asks for the first five sections. Unit 6 adds the five below them.

     Everything is pasted as TEXT. No screenshots, no images.

     ⚠️ The confusion matrix especially. The notebook prints one as a markdown
     table, ready to copy. A screenshot of a matrix earns nothing. Paste the
     table.
     ───────────────────────────────────────────────────────────────────────── -->

<!-- ═══════════════════════ UNIT 5 — THE BUILD ═══════════════════════ -->

## What This Does

<!-- Your community, and what your classifier sorts posts into. Three or four
     sentences. -->

I picked the Options subreddit community, www.reddit.com/r/options/.

---

## Label Taxonomy

<!-- Each label: a one-sentence definition and two real examples from your
     reading. Then your decision rule for the hardest boundary.

     The decision rule is worth a point on its own and it's the thing most
     people leave out. Every taxonomy has a hardest boundary. Name yours. -->

### `trade_log`

**Definition:**
Posts where the primary purpose is to report a specific options position that was opened, managed, or closed, including its entry, rationale, or P/L

**Example 1:**
>NVDA — right play, wrong expiration 🤦‍♀️

r/options - NVDA — right play, wrong expiration 🤦‍♀️
Bought 25 NVDA $225C 9/30 at $2.88, about $7.2k total.

The play is a short-term sympathy run into MU earnings next week. My thinking is that if MU gets a pre-earnings run and semis stay strong, NVDA could catch some of that momentum.

I picked the $225 strike because NVDA was trading around $225, so I wanted basically ATM calls rather than going far OTM.

The dumb part: I bought 9/30 by mistake. I actually wanted more time because I don’t want theta eating me alive while waiting for the setup.

Plan is to see what NVDA does Monday. If I get the move I’m looking for, I’ll close these and move into the expiration I originally wanted. If the setup breaks, I’m not planning to sit around praying until expiration.
Until then, part of my risk management is basically hoping Trump stays the fuck away from social media this weekend.

**Example 2:**
>Papakong88 0DTE - Exit Plan Modification (October 16, 2026)
In June, 2026 I changed my exit plan from a rollout to a buyback strategy. As a result of several buybacks, the income has been flat because each buyback cost several weeks of income. I changed the strategy back to a rollout on October 8. 
Details of the October 8 rollout is in https://www.reddit.com/r/options/comments/1udyri5/comment/pexxs85/?context=3
I have two more rollouts on October 14, 2026.
Rollout #1:
Roll the 29760 PS out 1 day and down 335 points to 29425 for 3.81 debit. (Buying back would have cost $10.)
On the next day, the 29425 was rolled down 125 points to 29300 with same day expiration for 1.75 debit.
The 29300 expired.
Rollout #2:
Roll the 29725 PS out 1 day and down 375 points to 29350 for 1.81 debit. (Buying back would have cost $8.)
The 29350 expired.
The cost of the rollouts were reduced by selling some junks.

### `educational`

**Definition:**
Posts where the primary purpose is to ask for or give an explanation of how options mechanics or strategy concepts work

**Example 1:**
>Help understand calls on 2-3x leverage stocks
As the title says, I’m looking for info on trading options on tickers such as RKLX or IONX. Rocketlab 2x and IonQ 2x. It seems like there is crazy reward for minimal risk but I must be missing something?

Has anyone done trades with leveraged stocks or etfs and had success? or even horror stories?

Thank you

**Example 2:**
>Questions about managing assignment exposure compared to max-loss risk
Do you set a separate limit for potential assignment exposure on defined-risk options trades, in addition to your max-loss limit? If so, how do you measure it?

For example, suppose I have a $100,000 account and limit each trade’s defined max loss to 1% ($1,000). I sell one Amazon Nov. 20, 2026 $230/$225 put credit spread for a potential $100 max profit and potential $400 max loss.

The spread is within my max-loss rule. If the short $230 put is assigned, I could be required to buy 100 shares for $23,000, even though the spread’s defined max loss is much smaller.

How would you, or do you, set a guardrail for potential assignment exposure, especially across multiple positions? For example, if 10 positions had a combined defined max loss of $10,000 but a gross assignment value of $150,000, how would you limit that exposure? Would you cap that assignment exposure at a percentage of your account (e.g. 30%), and limit the number or size of positions accordingly?

Thank you!

### `market_opinion`

**Definition:**
Posts where the primary purpose is to state a view or prediction about market direction, news, or conditions.

**Example 1:**
>Will most retail options trading be automated in 5 years?
I still open most of my spreads by hand but I've started letting alerts handle exits and rolls. Brokers keep making it easier to hand off the boring parts. Feels like in a few years a lot of retail flow will just be rules running on their own. Anyone here already fully automated on options, or is it still mostly clicking buttons? What part would you never hand off?

**Example 2:**
>Let's short TTWO
Nobody buy GTA 6 everybody just buy shorts or whatever (idk how it works)

### The hardest boundary

**Which two labels:**
trade_log and educational

**The decision rule I used every time:**
<!-- e.g. "If the post names a specific checkable fact, it's `analysis`, even
     if the tone is heated." -->
If a post includes specific options setup or actual trade executed but the primary intent is asking a question or clarification on options mechanics or strategy concept, it should be label'ed 'educational'. Only label a post as 'trade_log' if the primary intent is sharing aa trade execution, journal entry, setup breakdown, or profit/loss portfolio without seeking educational assistance.

---

## The Dataset

<!-- Where you collected from, how you labelled, your counts, and three hard
     cases. -->

**Where the posts came from:**

**How I labelled them:** <!-- Cold first? Pre-labelled with AI and corrected?
Say so plainly — the disclosure is required, not penalised. -->

**Counts per label:**

| Label | Count | Share |
|---|---|---|
|  |  |  |
|  |  |  |
|  |  |  |
| **Total** |  | 100% |

**Three hard cases**

<!-- Any post that made you pause: what it was, which two labels it could have
     been, and what you chose. These are worth more than the easy 190. -->

**1.**
> *The post:*
>
> *Could have been:*
>
> *I chose, because:*

**2.**
> *The post:*
>
> *Could have been:*
>
> *I chose, because:*

**3.**
> *The post:*
>
> *Could have been:*
>
> *I chose, because:*

---

## The Training Run

<!-- Your starting model, your settings, and anything you changed and why. -->

**Base model:**

**Settings:** <!-- epochs, learning rate, batch size, seed -->

**Anything I changed from the defaults, and why:**

**Split sizes:** <!-- train / val / test, and per-label counts in the test
split. If a label had fewer than about 8 in test, say so — it explains a lot
of next unit's variance. -->



---

## How I Used AI

<!-- Two specific moments — what you asked, what came back, what you changed.

     ⚠️ Plus disclosure of any pre-labelling. If you had a model pre-label a
     batch and then read and corrected every one, say that. It's an allowed
     workflow and disclosing it costs you nothing. Not disclosing it is the
     problem. -->

**Moment 1**

- *What I asked for:*
Here are 3 labels and its definitions. Write eight posts that sit on my boundaries.

trade_log: Posts that describes a specific options setup or actual trade executed
educational: Posts that asks or answers questions about clarification on options mechanics or strategy concepts.
market_opinion: Posts that comments on market direction predictions, news reactions, or general market conditions.
- *What came back:*
```
Here are eight posts that sit on the boundaries between the labels. Each has a note on which two labels it straddles and why.

1. trade_log / educational

Opened a 45 DTE put credit spread on SPY, 520/515, for $1.35 credit. I always choose a short strike near 0.20 delta because it roughly maps to an 80% chance of expiring OTM. Does that delta-as-probability rule hold up, or is it too simplistic?

Describes an actual trade, but the real question is about how delta relates to probability.

2. trade_log / market_opinion

Sold a covered call on my NVDA shares at the 140 strike for next Friday. Honestly I think this thing is topping out here after that run, so I’m happy to cap my upside for the premium.

A specific executed trade, but the justification is a directional call on the stock.

3. educational / market_opinion

With VIX sitting under 14, is it still worth selling premium? I keep hearing that low IV means options are “cheap” and the market is complacent, but does low IV actually mean a move is coming?

An options-mechanics question (IV and premium selling) wrapped in commentary on market conditions.

4. trade_log / educational

Got assigned on my short 50 put in AMD this morning, 100 shares at $50. Now I’m holding stock at a cost basis of $48.20 after the premium. Is it better to start selling covered calls right away or wait for a bounce?

Reports a real assignment and its outcome, but the ask is a strategy-concept question.

5. market_opinion / educational

Everyone says the Fed cutting rates is bullish, but I’ve noticed call options on the indexes often get crushed right after the announcement even when the market rallies. Why does that happen, and does it mean a rally can’t be trusted?

Reacts to a news event and market behavior, but the core is explaining IV crush.

6. trade_log / market_opinion

Closed my SPX iron condor for a 40% profit yesterday. The market just chopped sideways all week like I expected, and I think this range-bound grind continues through month end. Planning to put on another one Monday.

Documents a closed trade, but spends equal weight forecasting where the market goes next.

7. educational / trade_log

Say I buy a TSLA 250 call for $8 with the stock at 245, and it’s up to 252 at expiration. Do I make money? Walking through my own example, I think I’m at breakeven at 258, so I’d lose $6 on this.

A hypothetical-style mechanics question framed with concrete numbers that read like a real position.

8. market_opinion / educational

People keep saying the market is “pricing in” a soft landing. Isn’t that just saying options implied moves already reflect the consensus? Trying to understand if there’s any edge in fading consensus when skew looks like this.

A general market-conditions comment that leans on an options-concept question about implied moves and skew.

If you’d like, I can write more that target one specific pair of labels, or make them harder by removing the giveaway keywords.
```
- *What I changed:*
I try grounding the definiton better with the post's primary purpose.

trade_log: Posts where the primary purpose is to report a specific options position that was opened, managed, or closed, including its entry, rationale, or P/L.
educational: Posts where the primary purpose is to ask for or give an explanation of how options mechanics or strategy concepts work
market_opinion: Posts where the primary purpose is to state a view or prediction about market direction, news, or conditions.

**Moment 2**

- *What I asked for:*
Here are five acceptance criteria with targets, for a text classifier I have not trained yet. For each target, give me one reason it might turn out too easy and one reason it might turn out too hard. Don't tell me which is more likely and don't suggest different numbers.

1.Overall classification accuracy is at least 67%.
2.No single label accounts for more than 60% of the total dataset.
3.When another human or AI model labels against the 20 cold labeled posts, atleast 85% should be in agreement.
4.When a model has high confidence on a label, it's accuracy should be atleast 85%
5.The precision score for trade_log label is atleast 90%
- *What came back:*
```
1. Overall accuracy ≥ 67%

Too easy: If the label distribution is skewed, a model that mostly predicts the majority class can clear 67% without learning anything useful. Accuracy also rewards the common labels and hides failures on rare ones.
Too hard: If the labels are subjective or overlap (a post could reasonably be two categories), the ceiling is set by label noise, and no model can reliably exceed what the annotators themselves agree on.

2. No single label > 60% of the dataset

Too easy: This constrains the dataset, not the classifier. It’s satisfied by how the data was collected or sampled, even if the classes are trivially separable or the minority labels are tiny but still nominally “enough.”
Too hard: If the real-world population is naturally dominated by one kind of post (say, most posts are chatter), reaching 60% or less may require heavy oversampling or hunting for rare examples, which can be slow and can distort how representative the data is.

3. ≥ 85% agreement on the 20 cold labeled posts

Too easy: With only 20 posts, one or two lucky or unlucky items swing the number a lot, and if the cold posts happen to be clear-cut examples, agreement will be high regardless of how well your label definitions hold up on messy cases.
Too hard: 85% of 20 means at most 3 disagreements, and with a small sample plus ambiguous label boundaries, a couple of genuinely borderline posts can sink you even when the labeling scheme is reasonable. Different human or model labelers can also interpret the guidelines differently from you.

4. High-confidence predictions ≥ 85% accurate

Too easy: If “high confidence” is defined by a strict threshold, only a small slice of easy, prototypical examples may qualify, so the accuracy of that slice looks great while most predictions are never covered by the criterion.
Too hard: Models are often poorly calibrated, especially overconfident on out-of-distribution or ambiguous posts, so confident errors can pull accuracy in that bucket below 85%. If the threshold is loose and lets in many predictions, the bucket gets diluted with errors.

5. Precision for trade_log ≥ 90%

Too easy: If trade_log has distinctive surface features (tickers, entry/exit prices, specific formatting), a conservative model that only predicts it when those cues appear can hit high precision, and precision ignores how many true trade_log posts it misses.
Too hard: If trade_log is a minority class or shares vocabulary with neighboring labels (trade ideas, commentary, recaps), even a few false positives drag precision down, and 90% leaves little room for confusion with those lookalike categories.
```
- *What I changed:*
I lowered criterion 3 from 85% to 80% because it might be too hard on small sample size.

**Pre-labelling disclosure:**

<!-- ═══════════════════════ UNIT 6 — THE TEST ═══════════════════════

     Don't fill these in during unit 5.
     ═══════════════════════════════════════════════════════════════════ -->

---

## Baseline vs. Trained

<!-- Both models on the same posts. `python baseline.py --trained results.json`
     prints this table for you. -->

| Measure | Baseline | Trained | Difference |
|---|---|---|---|
| Overall accuracy |  |  |  |
| Macro F1 |  |  |  |
| F1 — `label_one` |  |  |  |
| F1 — `label_two` |  |  |  |

**What I predicted before I looked:**
<!-- Milestone 1 asks you to write this BEFORE seeing the trained numbers. A
     prediction made afterwards isn't one. -->

**What the gap actually means:**
<!-- If the baseline matched your trained model, your fine-tuning added
     nothing — and that is a real finding, not a failure. Say it plainly. -->



---

## Run Log — Before

<!-- Five criteria across three seeds. The notebook's section 6 prints the
     spread table; the Target and Verdict columns are yours. -->

| Criterion | Target | Seed 42 | Seed 7 | Seed 2024 | Verdict |
|---|---|---|---|---|---|
| 1.  |  |  |  |  |  |
| 2.  |  |  |  |  |  |
| 3.  |  |  |  |  |  |
| 4.  |  |  |  |  |  |
| 5.  |  |  |  |  |  |

### Confusion matrix

<!-- ⚠️ TYPED AS A MARKDOWN TABLE. The notebook prints one ready to paste.
     An image of a matrix earns nothing. -->

| true \ predicted |  |  |  |
|---|---|---|---|
| **** |  |  |  |
| **** |  |  |  |
| **** |  |  |  |

**My biggest off-diagonal number, and what it means:**
<!-- Not "the model made mistakes" — WHICH boundary it didn't learn, and which
     direction. "7 real analysis posts were called hot_take and only 3 went the
     other way" is a direction, not just an error rate. -->



---

## Verdicts and Diagnoses

<!-- MET or MISSED against LAST UNIT's target. The target has to hold across
     all three seeds, not turn up sometimes. -->

| # | Criterion | Target | Verdict | How I decided |
|---|---|---|---|---|
| 1 |  |  |  |  |
| 2 |  |  |  |  |
| 3 |  |  |  |  |
| 4 |  |  |  |  |
| 5 |  |  |  |  |

**Diagnoses**

<!-- For each miss: the cause, and how you know. The four common causes are:
     too few examples for a label, a boundary you applied inconsistently, a
     genuinely hard label pair, and a task the model can't reach from this
     much data.

     ⚠️ Use your agreement report as evidence. It is the only instrument you
     have that can tell a LABELLING problem from a MODEL problem, and this
     section is graded on whether you used it that way. -->



---

## Agreement Report

<!-- Your rate against the staff set, and every disagreement adjudicated.

     Remember you labelled these 30 under the STAFF taxonomy in
     data/staff_taxonomy.md, not your own — so every argument below is made
     from those definitions and those decision rules. -->

**Agreement rate:** ___ / 30 = ___%

<!-- Nobody grades this number. A 60% who argues every disagreement from the
     stated rules beats a 95% who wrote "staff was right" nine times. Several
     of the 30 were chosen because they're genuinely ambiguous — you should be
     winning some of these. -->

**Disagreements**

<!-- Three lines each: the post, both labels, and who you think is right and
     why — grounded in the staff definitions you were both applying.

     Then sort each into one of three piles:
       (a) the rule covered it and I applied it loosely → a consistency problem
       (b) the rule genuinely doesn't say               → a gap in the definitions
       (c) the rule is ambiguous here and my reading is defensible → argue it.
           This is a legitimate win.

     Pile (a) is the one that matters most for your diagnosis: if you applied a
     written rule two different ways on 30 posts, that is direct evidence about
     what you did across your own 200. -->

**1.**
> *The post:*
>
> *Staff said / I said:*
>
> *My call, and why:*
>
> *Which pile:*

**2.**
> *The post:*
>
> *Staff said / I said:*
>
> *My call, and why:*
>
> *Which pile:*

**What the pattern in my disagreements tells me:**



---

## The Improvement

**What I changed:**

**Which diagnosis pointed at it:**

### Run Log — After

| Criterion | Target | Seed 42 | Seed 7 | Seed 2024 | Verdict |
|---|---|---|---|---|---|
| 1.  |  |  |  |  |  |
| 2.  |  |  |  |  |  |
| 3.  |  |  |  |  |  |
| 4.  |  |  |  |  |  |
| 5.  |  |  |  |  |  |

**Did it help, and how do I know:**

<!-- If it didn't, say so. Relabelling that didn't help is a genuinely
     interesting result and earns full credit. -->



---

## What's Still Broken

<!-- For each criterion still missed: what you'd do, and why you stopped. -->



**The gap between what I meant my labels to capture and what the model
learned:**
<!-- Two sentences. Your confusion matrix is the evidence. -->



<!-- ═════════════════════════════════════════════════════════════════════

     SUBMISSION CHECKLIST — unit 5

       [ ] criteria.md has five numbered criteria, each naming a NUMBER
       [ ] Each has a reason underneath tied to your data or taxonomy
       [ ] labels.csv: at least 150 rows, text/label/note, ONE file not split
       [ ] No label above 70%
       [ ] All five unit 5 sections have real content
       [ ] Label Taxonomy includes the decision rule for your hardest boundary
       [ ] The Dataset includes three hard cases
       [ ] results.json and test_split.csv committed (the notebook does this)
       [ ] At least four new commits
       [ ] Repository URL submitted — WRITE IT DOWN

     SUBMISSION CHECKLIST — unit 6

       [ ] Baseline vs. Trained table, with your prediction written beforehand
       [ ] Run Log — Before, five criteria across three seeds
       [ ] Confusion matrix TYPED AS A MARKDOWN TABLE
       [ ] A verdict on every criterion
       [ ] A diagnosis for every miss, using the agreement report as evidence
       [ ] Agreement Report with every disagreement adjudicated
       [ ] One improvement, with Run Log — After
       [ ] What's Still Broken
       [ ] results_three_seeds_before.json, results_three_seeds_after.json,
           baseline_results.json and
           agreement_results.json committed
       [ ] At least four new commits
       [ ] The SAME repository URL as last unit

     Do not delete and recreate this repository.
     ═════════════════════════════════════════════════════════════════════ -->

---

📖 **How to run this project: [RUNNING.md](RUNNING.md)**
