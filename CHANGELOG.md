# Changelog

## 0.2.0 — 2026-10-07

Counterexamples are now treated as possible theory, not merely as failures to exclude.

- Added counterexample triage: EXCLUDE / ABSORB / UNRESOLVED.
- Added a dedicated counterexample-promotion / theory-expansion stage.
- The default rule is now: if a counterexample is robust, admissible, and structurally interesting, keep the deleted assumption deleted and promote the failure into a regime/result.
- Added regime-style endpoints such as O=>Y and not-O=>Z.
- Added an `absorb` mode.
- Updated the minimal example to turn multiplicity into a positive failure theorem rather than merely restoring strict monotonicity.
- Updated README and prompt language to discourage "repairing away" interesting failures.

## 0.1.0 — 2026-10-07

Initial public protocol draft.

- Formalized assumption ablation.
- Added proof/counterexample/open-obligation certificates.
- Added obstruction extraction.
- Added necessity/sufficiency and theorem-reversal stages.
- Added primitive/observable reduction.
- Added information-advantage and nearby-failure stages.
- Added dependency-DAG reconstruction.
- Added statement-status and verification ledgers.
- Added stop conditions to prevent meaningless assumption minimization.
- Added de-dialogue rewrite and novelty-audit stages.
