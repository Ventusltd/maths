# Circles, radius, diameter and pi

## The problem

A circle has no straight side to measure.

So we need simple measurements that describe its size.

## Radius

The **radius** is the distance from the centre of the circle to its edge.

If the radius is 3 m, every point on the edge is 3 m from the centre.

## Diameter

The **diameter** goes from one edge, through the centre, to the opposite edge.

It is twice the radius.

```
radius = 3 m
diameter = 6 m
```

## Circumference

The circumference is the distance around the outside of the circle.

## Where pi comes from

For every circle, no matter how large or small:

```
circumference ÷ diameter
```

is always the same number.

That number is called **pi**:

```
π ≈ 3.141592653589793...
```

So if the diameter is 10 m, the distance around the circle is about:

```
10 × π ≈ 31.416 m
```

Pi is not an arbitrary decoration. It appears because circles have the same circumference-to-diameter ratio at every scale.

## Technical maths

Diameter:

$$
d=2r
$$

Circumference:

$$
C=\pi d=2\pi r
$$

Definition of pi:

$$
\pi=\frac{C}{d}
$$

Pi is irrational, so its decimal expansion does not terminate or repeat.

## Try it in Excel

| cell | type | expect |
|---|---|---|
| A2 | `3` (radius) | 3 |
| B2 | `=2*A2` (diameter) | 6 |
| C2 | `=PI()*B2` (circumference) | 18.849556 |
| D2 | `=C2/B2` | 3.141593 |

Change A2 to anything. D2 never changes: that is pi.

## Check it yourself

1. Diameter 10 m: circumference? (31.415927 m)
2. Radius 1: how far round? (2π = 6.283185)
3. Wrap a string round a tin, then measure across. Divide. Close to 3.14?

## Sources / further reading

- NIST Digital Library of Mathematical Functions: https://dlmf.nist.gov/
- OpenStax, *Precalculus 2e*: https://openstax.org/details/books/precalculus-2e
