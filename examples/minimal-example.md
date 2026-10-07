# Minimal example: splitting existence from uniqueness

This toy example illustrates the protocol without claiming any novelty.

## Bundled starting theorem

Suppose a function f:[0,1] -> R satisfies:

- A1: f is continuous.
- A2: f is strictly increasing.
- A3: f(0) < 0.
- A4: f(1) > 0.

Claim T: there exists a unique x* in (0,1) such that f(x*) = 0.

## Ablate A2

Remove strict monotonicity.

A1 + A3 + A4 still imply existence by the intermediate value theorem, but uniqueness can fail.

Example:

f(x) = (x - 1/4)(x - 3/4).

This particular example does not satisfy the endpoint signs above, so it is not yet a valid certificate. The protocol therefore rejects it rather than casually using it.

A valid example is instead constructed to preserve A1, A3, and A4 while creating multiple zeros, for example a continuous piecewise-linear function passing through

(0,-1), (1/4,0), (1/2,-1), (3/4,0), (1,1).

Thus:

- A2 is not needed for existence.
- Some uniqueness condition is needed for uniqueness.

## Dependency split

The original bundled dependency

A1 + A2 + A3 + A4 -> existence + uniqueness

can be reorganized as:

A1 + A3 + A4 -> existence

A2 -> at most one zero

and therefore

A1 + A2 + A3 + A4 -> unique zero.

The theorem is now logically cleaner because existence and uniqueness no longer inherit the same parent assumptions.

## Ablate A1

Keep A3 and A4 but remove continuity.

Define

f(x) = -1 for x < 1/2,
f(x) = 1 for x >= 1/2.

Then f(0)<0 and f(1)>0, but f has no zero.

The counterexample reveals the obstruction: endpoint sign reversal alone does not force the function to attain intermediate values.

Continuity is sufficient, but the proof only uses the intermediate value property. This suggests a repaired existence theorem:

> If f has the intermediate value property on [0,1], f(0)<0, and f(1)>0, then f has a zero in (0,1).

This is a reduction from a stronger regularity assumption (continuity) to the exact property used by the argument.

## Lesson

The point is not the elementary theorem. The point is the research move:

bundled theorem -> ablation -> valid counterexample -> obstruction -> split dependencies -> weaker interpretable condition.
