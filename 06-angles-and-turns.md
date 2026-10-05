# Angles and turns

## The problem

A distance from the centre tells us **how far** to go.

It does not tell us **which direction** to go.

Angles solve that problem.

## Degrees

A complete turn around a circle is divided into:

```
360 degrees
```

Common directions:

```
0°    right
90°   up
180°  left
270°  down
360°  back where we started
```

So an angle is simply a way of describing direction around a centre.

Angles count **anticlockwise**: 90° is a quarter turn to the left.

Careful: on many computer screens Y counts **downwards**, which flips the picture and makes the same angles look clockwise. Always check which way Y goes.

## Why 360?

The choice of 360 is ancient and convenient because 360 can be divided evenly by many useful numbers: 2, 3, 4, 5, 6, 8, 9, 10, 12 and more.

The geometry would still work with another full-turn unit; mathematics also uses **radians**.

## Radians

In radians, one complete turn is:

```
2π radians
```

So:

```
180° = π radians
360° = 2π radians
```

Computers and mathematical functions often use radians.

## Why care?

In Kuiper:

- radius tells us how far from the centre a point belongs;
- angle tells us which direction from the centre it belongs.

We need both.

## Technical maths

Degree-to-radian conversion:

$$
\theta_{rad}=\theta_{deg}\frac{\pi}{180}
$$

Radian-to-degree conversion:

$$
\theta_{deg}=\theta_{rad}\frac{180}{\pi}
$$

## Try it in Excel

Excel's COS and SIN want radians.

| cell | type | expect |
|---|---|---|
| A2 | `180` (degrees) | 180 |
| B2 | `=RADIANS(A2)` | 3.141593 |
| C2 | `=DEGREES(B2)` | 180 |
| D2 | `=A2/360` (fraction of a turn) | 0.5 |

## Check it yourself

1. A quarter turn in degrees and in radians? (90°, π/2 = 1.570796)
2. 0.25 of a turn is how many degrees? (90)
3. 0.618034 of a turn is how many degrees? (222.49, the Kuiper wafer's step)

## Sources / further reading

- OpenStax, *Precalculus 2e*: https://openstax.org/details/books/precalculus-2e
