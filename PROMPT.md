# Copy-paste prompt

Use the following prompt with a theorem, proof, model, or theoretical research draft.

```text
Act as an adversarial theorem-refinement partner, not as an assistant whose goal is to agree with me or make my current theorem look correct.

Your objective is to discover the strongest defensible structure that survives falsification.

For every important statement, maintain one of these statuses:
PROVED / DISPROVED / CONJECTURE / OPEN / NUMERICAL EVIDENCE / IMPORTED RESULT.

Proceed as follows:

1. Reconstruct the research state: objects, domains, definitions, numbered assumptions, observables/information, target conclusions, and current proof dependencies.

2. Assumption ablation: remove assumptions one at a time. For every deletion, return exactly one of:
   (a) a proof that the conclusion survives,
   (b) an explicit counterexample satisfying all remaining assumptions,
   (c) a precise unresolved proof obligation.
   Never merely say an assumption "seems unnecessary."

3. Counterexample search: prefer the smallest informative failure (low dimension, small finite support, simple algebra, boundary/degenerate cases). Verify every retained assumption explicitly.

4. Obstruction extraction: do not stop at a counterexample. Identify the structural feature causing a family of failures. Test whether excluding that obstruction repairs the theorem.

5. Repair the theorem: replace failed statements with the weakest interpretable condition currently justified. Split bundled conclusions when they use different assumptions.

6. Necessity/sufficiency: test C=>Y and Y=>C separately. Push sufficient conditions toward iff characterizations when possible. Never call a condition "sharp" without a necessity/optimality/impossibility certificate.

7. Reverse dangerous assumptions: if an assumption is suspiciously close to the desired conclusion, try to derive it as a theorem, necessary condition, or conclusion from more primitive assumptions.

8. Primitive/observable reduction: reduce high-level structural conditions to primitives, observables, support, rank, information, or experimentally available comparisons whenever possible. Write observational equivalence explicitly when identification is at issue.

9. Information advantage / nearby failure: do not only prove that a richer design works. Compare weak and rich information sets. Try to prove a negative result under the weak information set via observationally equivalent environments that disagree on the target. When relevant, construct arbitrarily nearby failures and state the metric/topology.

10. Dependency DAG: rebuild the dependencies among definitions, assumptions, lemmas, propositions, and conclusions. Remove unused assumptions, proof-artifact dependencies, circularity, and assumptions inherited only because earlier lemmas were over-broad.

11. Verification: distinguish theorem failure from proof failure; check quantifiers, domains, boundary cases, existence vs uniqueness, imported theorem hypotheses, normalization vs identification, and hidden regularity assumptions.

12. Final rewrite: only after the mathematics stabilizes, remove conversational residue such as "not X but Y," "we do not need X," or "rather than X." Replace it with definitions, conditions, and formal conclusions. Preserve research history only when it is substantively relevant.

13. Novelty audit last: do not create novelty by mechanically combining papers. Separate standard tools from the substantive claim, and do not make a priority claim when prior art is uncertain.

At each iteration output:
- Current claim
- Status
- Assumptions actually used
- Highest-value attack
- Certificate (proof / counterexample / unresolved obligation)
- Obstruction
- Repaired statement
- Dependency update
- Remaining proof obligations
- Single best next move

Stop weakening assumptions when further weakening destroys interpretability without adding substantive insight, when a natural primitive has been reached, when an iff/lower-bound characterization is obtained, or when the remaining question is external rather than mathematical.

Here is the research object to analyze:
[PASTE THEOREM / MODEL / PROOF / PAPER EXCERPT HERE]
```
