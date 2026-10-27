# Acceptance criteria — TakeMeter

Five criteria that say what "working" means for this classifier, written in
unit 5 **before** anything was trained.

**All five are yours this time.** None are given. You've had two projects of
practice.

An acceptance criterion names a number. *"The model is accurate"* is an
opinion. *"Every label has an F1 of at least 0.60 on the held-out set"* is a
criterion.

Under each, write a sentence or two on **why that number**. A reason that says
something about your data or your taxonomy earns credit — *"I picked 0.60 F1
for `reaction` because it's my smallest label and I only have about 50
examples of it"*. A reason that could be attached to any project does not.

> Missing your own targets next unit costs you nothing. Setting a target so
> easy you can't miss it does.

---

## Pick numbers you can defend

Not numbers that sound impressive. Three labels means a coin-flip guesser gets
about 33%, so a target of 0.40 is barely a target. Your number should sit
somewhere you'd honestly call useful.

**Cover at least three of these five areas.** They're here as prompts, not as a
form to fill in — a criterion that fits none of them is fine if it names a
number.

| Area | A question it could answer |
|---|---|
| Overall accuracy | How often does it need to be right to be worth using? |
| Per-label performance | Is one label allowed to be much worse than the others? |
| Balance | How lopsided can your label counts get before it's a problem? |
| Consistency | If someone else labelled the same posts, how often should you agree? |
| Confidence | Should a confident prediction be right more often than an unsure one? |

Two things worth knowing before you pick numbers, because both will affect
whether you hit them:

- **Your smallest label will have the jumpiest score.** If a label has 50
  examples, about 8 land in the test split. An F1 computed on 8 examples moves
  a lot between seeds. A target for that label should be looser than one for
  your biggest label, and saying so is a good reason.
- **Unit 6 tests across three seeds, and the target has to hold across all
  three.** A target of 0.65 against results of 0.71, 0.62, 0.68 is a **miss**.
  Pick with that in mind — it is stricter than it first sounds.

---

## 1.

<!-- Your criterion. It must name a number. -->
Original: Overall classification accuracy is at least 67%.
Revised: Overall classification accuracy is at least 50%


**Why this target:**
Original: A random guesser has 33.3% accuracy across 3 labels, so I'm targeting double that accuracy at 67%.
Revised: A random guesser has 25% accuracy across 4 labels, so I'm targeting double that accuracy at 50%. Also the test split for 3 of the label only have 4 examples so low sample size to test against, may/probably will affect the accuracy. Note: Change this based on Unit 5 submission feedback.


---

## 2.

<!-- Your criterion. -->
No single label accounts for more than 60% of the total dataset.


**Why this target:**
The notebook does 70/15/15 split, 10% buffer under the 70% otherwise the model could be wrongly fine-tuned to just guess the major label.


---

## 3.

<!-- Your criterion. -->
When another human or AI model labels against the 20 cold labeled posts, atleast 80% should be in agreement.


**Why this target:**
Initially targeted 85% because boundary posts and 7 out of 8 post that the AI stress-tested against my labels definition were label'ed. I lowered the targeted to 80% from how I used AI portion to increase safe buffer on small sample size of 20 cold posts.


---

## 4.

<!-- Your criterion. -->
Original: When a model has high confidence on a prediction, it's accuracy should be atleast 85%
Revised: When a model has high confidence (> 0.80) on a prediction, it's accuracy should be atleast 85%
Revised 2: The accuracy of the most confident third should atleast be 85%.


**Why this target:**
Original: I target 85% because a model with high confidence on it's prediction should have high accuracy to be useful. 15% safe buffer and it's about 15% more accurate than the baseline 67% overall accuracy.
Revised: Same as original but added (> 0.80) confidence score based on Unit 5 submission feedback
Revised 2: The idea and intent is the same with the same target of 85%. However instead of a single confidence score which I'm not sure if I can extract/edit the notebook without affecting the future test runs, I will use the confidence result data that I actually have which is most confident third.


---

## 5.

<!-- Your criterion. -->
The precision score for trade_log label is atleast 90%


**Why this target:**
I targeted 90% for trade_log because the label definition and the decision rule should make this a almost binary yes or no label, 10% for safe edge case buffer.


---

<!-- ─────────────────────────────────────────────────────────────────────────
     UNIT 6 — read this before you change anything above.

     If a criterion turns out to be BROKEN rather than merely unmet, you can
     revise it, and that earns credit. But never delete or edit the original
     line. Add the revision underneath, like this:

         ## 2. Every label performs acceptably

         The model performs well on all labels.

         **Why this target:** ...

         > **Revised in unit 6:** Every label has an F1 of at least 0.60 on
         > the held-out set.
         >
         > **Why revised:** "performs well" gave me nothing to check. I
         > couldn't produce a verdict from it at all.

     That's a revision because the criterion couldn't be MEASURED.

     Lowering a target because you missed it is not a revision, and it costs
     you the point:

         ✗ "Overall accuracy of at least 0.65" → "at least 0.55", because
            0.65 turned out to be optimistic for 200 examples.

     A number you missed stays where it is, gets diagnosed, and gets a fix
     attempted. That's where the points are.
     ───────────────────────────────────────────────────────────────────────── -->
