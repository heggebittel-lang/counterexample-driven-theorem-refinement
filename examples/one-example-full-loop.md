# One example, one full research loop

This elementary example shows how several CDTR operations connect. It is
**not** a new mathematical result and should not be presented as one.

## Starting point

Consider the class

`F = {f:[0,1] -> R : f is continuous, f(0)=-1, f(1)=1}`.

The intermediate value theorem establishes

> Every f in F has at least one zero in (0,1).

If we additionally assume strict increase, the zero is unique.

## 1. Remove the uniqueness assumption

Delete strict increase, but keep continuity and both endpoint values.

Consider

`f1(x) = 2x - 1`

and

`f2(x) = (32/3)(x-1/4)(x-1/2)(x-3/4)`.

Both are continuous. Direct calculation gives

- `f1(0)=f2(0)=-1`;
- `f1(1)=f2(1)=1`;
- `f1` has exactly one root: `1/2`;
- `f2` has exactly three roots: `1/4, 1/2, 3/4`.

This is an exact counterexample to the claim that continuity and these
endpoint values force uniqueness.

## 2. Absorb rather than exclude

Do not restore strict increase solely to eliminate `f2`.

Keep both examples inside the admissible model space. The question is now
what further properties determine the structure of the zero set.

The single example establishes *possibility*, not a complete classification.
A theorem for the whole complement of strict increase would need a separate
proof; failure of monotonicity does not by itself imply multiple roots.

## 3. Factor the dependencies

Separate two useful statements:

- continuity AND opposite endpoint signs => at least one zero;
- strict increase => at most one zero;
- existence AND at-most-one => exactly one zero.

This is more informative than repeating the strong assumptions in the
statement of every downstream result. Another sufficient condition for
at-most-one zero can be substituted without changing the existence argument.

Strict increase is a **sufficient** condition, not a necessary one. Do not
accidentally claim the converse.

## 4. Extract an information boundary

Suppose the observer sees only

`Obs(f) = (f(0), f(1))`

and knows that the unknown function is continuous.

Then

`Obs(f1)=Obs(f2)=(-1,1)`,

yet `f1` and `f2` disagree on the property

`U(f) = "f has exactly one root on (0,1)"`.

Therefore `U` is **not identified by endpoint observations** over the
class F.

This is a negative information result, with a concrete certificate.
It does not imply that strict monotonicity is the weakest possible extra
information or that no other measurements could identify U.

## 5. Formalize the final statements

Prefer stating the following separate mathematical facts:

1. Continuity and opposite endpoint signs guarantee existence.
2. Strict increase guarantees at most one zero.
3. There are continuous functions with identical endpoint values and
   different numbers of zeros.

Do not stop at the vague diagnostic "we cannot guarantee uniqueness,"
but do not falsely replace it with "non-monotonicity implies nonuniqueness."

## 6. Communicate it to a reader

In a first-person essay, the point can be phrased conversationally:

> If the second function meets the conditions I actually care about,
> why should I add an assumption just to throw it away?

That question is useful personal voice, not a flaw to be removed by a
formal-theorem rewrite.

In a proof, use definitions, propositions, and exact implications instead.

The same example can thus connect assumption deletion, counterexample
absorption, semantic dependency structure, identification failure, and
genre-appropriate exposition.
