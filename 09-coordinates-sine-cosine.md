# Coordinates, sine and cosine

## The problem

Suppose we know:

- how far a point is from the centre;
- which direction it is in.

A screen, map or drawing usually wants something different:

- horizontal position;
- vertical position.

Those are **X and Y coordinates**.

## Think of a point on a clock

If a point is 5 units from the centre, its radius is 5.

But depending on the angle, those 5 units are split between horizontal movement and vertical movement.

Sine and cosine perform that split.

## Cosine

Cosine tells us the horizontal share of the radius.

## Sine

Sine tells us the vertical share of the radius.

So:

```
X = radius × cosine(angle)
Y = radius × sine(angle)
```

This converts:

```
distance + direction
```

into:

```
horizontal position + vertical position
```

## Simple examples

At 0°:

```
cos = 1
sin = 0
```

So a radius of 5 becomes:

```
X = 5
Y = 0
```

At 90°:

```
cos = 0
sin = 1
```

So:

```
X = 0
Y = 5
```

## Technical maths

Polar coordinates \((r,\theta)\) convert to Cartesian coordinates \((x,y)\) by:

\[
x=r\cos\theta
\]

\[
y=r\sin\theta
\]

Trigonometric software functions normally expect \(\theta\) in radians.

## Sources / further reading

- OpenStax, *Precalculus 2e*: https://openstax.org/details/books/precalculus-2e
- NIST Digital Library of Mathematical Functions: https://dlmf.nist.gov/
