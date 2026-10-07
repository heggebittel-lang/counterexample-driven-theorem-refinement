# Counterexample-Driven Theorem Refinement (CDTR)

A structured AI-assisted workflow for mathematical and theoretical research.

CDTR is not a collection of magic prompt phrases. It is a research protocol for attacking a candidate theorem until its real assumptions, failure modes, dependency structure, and information requirements become explicit.

The core loop is:

**assumption ablation -> counterexample -> obstruction -> theorem repair -> necessity/sufficiency -> primitive reduction -> information lower bound -> dependency compression -> verification**

## Why this exists

Large language models make it cheap to generate proofs, examples, variants, and algebra. That does not automatically make a theory correct. A useful workflow therefore needs an adversarial objective: the model should be rewarded for killing weak claims, not for defending the user's first idea.

This repository turns that idea into a reusable protocol.

## Quick start

For the full protocol, use [`SKILL.md`](./SKILL.md).

For a single copy-paste prompt, use [`PROMPT.md`](./PROMPT.md).

For maintaining a long-running project, copy [`templates/RESEARCH_STATE.md`](./templates/RESEARCH_STATE.md) into your project and update it after each research iteration.

A tiny example is in [`examples/minimal-example.md`](./examples/minimal-example.md).

## What the protocol tries to do

1. Delete assumptions rather than automatically preserve them.
2. Require a proof, counterexample, or explicit open obligation for every attempted deletion.
3. Turn isolated counterexamples into structural obstructions.
4. Push sufficient results toward necessity and iff characterizations.
5. Turn suspicious assumptions into conclusions when possible.
6. Reduce abstract conditions to primitives, observables, support, or information.
7. Prove why extra information matters, rather than only showing that one design works.
8. Rebuild theorem/lemma dependencies as a DAG and remove assumption creep.
9. Track statement status so that conjectures are not silently promoted to theorems.
10. Remove conversational residue only after the mathematics has stabilized.

## What it is not

CDTR is not:

- a guarantee that an AI-generated proof is correct,
- a substitute for domain knowledge,
- a literature-gap generator,
- a paper-writing automation pipeline,
- a claim that every theorem should use logically minimal assumptions,
- a claim that counterexamples alone constitute theory.

The workflow explicitly keeps interpretability, verification, and domain meaning as constraints.

## Suggested usage

Give the model your current theorem, model, proof, or paper excerpt and invoke a mode such as:

- `diagnose`
- `ablate`
- `counterexample`
- `obstruction`
- `characterize`
- `primitive`
- `information`
- `dag`
- `verify`
- `rewrite`
- `full`

For serious work, prefer repeated short adversarial iterations over asking the model to "improve the whole paper" in one pass.

## Design principle: certificates, not confidence

The protocol does not treat model confidence as evidence.

Every important move should produce a checkable object:

- proof,
- explicit counterexample,
- observational-equivalence pair,
- impossibility construction,
- dependency graph,
- precise unresolved obligation.

A sentence such as "this assumption is probably unnecessary" is not an acceptable endpoint.

## Status vocabulary

Every substantive claim should be tagged as one of:

`PROVED` / `DISPROVED` / `CONJECTURE` / `OPEN` / `NUMERICAL EVIDENCE` / `IMPORTED RESULT`

This is deliberately boring. It prevents a productive conversation from quietly turning guesses into results.

## Origin

The workflow grew out of my own attempts to do theoretical research with AI. In one project, an initially proposed "exit mechanism" in a rational-addiction model was repeatedly attacked until the original mechanism interpretation failed; the surviving questions shifted toward compensated comparison, falsification, support, and identification. The experience suggested that AI was most useful when asked to attack and restructure a theory rather than merely defend it.

The historical research archive is here:

- https://github.com/heggebittel-lang/Rational-Relapse-Theory

A later preprint from that line of work is:

- *Closure and Curvature in Sparse Compensated Comparisons* (SSRN): https://papers.ssrn.com/sol3/papers.cfm?abstract_id=7363901

## Contributing

Issues and pull requests are welcome. Useful contributions include:

- counterexamples showing that part of the protocol is misleading,
- better stop conditions,
- domain-specific variants,
- examples where the workflow materially changes a theorem,
- verification templates,
- integrations with formal proof assistants.

Please do not submit large collections of generic prompt phrases unless they correspond to a distinct research operation with a checkable output.

## License

This repository's prompt text, documentation, and examples are licensed under **Creative Commons Attribution 4.0 International (CC BY 4.0)**.

You may share and adapt the material, including commercially, provided that appropriate attribution is given and changes are indicated. See the official license terms at https://creativecommons.org/licenses/by/4.0/.

Suggested attribution:

> Yushang Cheng, *Counterexample-Driven Theorem Refinement (CDTR)*, CC BY 4.0.

## Citation

If this workflow is useful in a public project, paper, course, or derivative prompt, attribution is appreciated and required by the license. A machine-readable citation file is included in [`CITATION.cff`](./CITATION.cff).
