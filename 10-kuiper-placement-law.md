# Kuiper placement law

This file combines the earlier ideas.

Read the earlier notes first if any symbol here feels unexplained.

## The problem

We want numbered objects to receive deterministic positions without manually storing a separate coordinate for every object.

Each object has a key:

```
1, 2, 3, 4, 5, ...
```

From that key we calculate:

1. how far from the centre it belongs;
2. which direction it belongs;
3. its X and Y position.

## Step 1: distance from the centre

Use:

```
radius = square root of key
```

So:

```
key 1  → radius 1
key 4  → radius 2
key 9  → radius 3
key 16 → radius 4
```

Why?

Because circle area grows with radius squared.

Using square root makes the area grow roughly in step with the number of keys.

## Step 2: direction

Use an angular rule that keeps wrapping around the circle and avoids simple repeating spokes.

A teaching version is:

```
angle = (key × 137.507764°) mod 360°
```

## Step 3: convert to X and Y

```
X = radius × cosine(angle)
Y = radius × sine(angle)
```

Now every key can generate a coordinate.

No individual coordinate needs to be typed by hand.

## Why the square root is important

For key \(k\):

\[
r=\sqrt{k}
\]

Circle area is:

\[
A=\pi r^2
\]

Substitute \(r=\sqrt{k}\):

\[
A=\pi(\sqrt{k})^2
\]

so:

\[
A=\pi k
\]

That is the important result.

As the key count grows, the available area grows linearly with it.

## Production Kuiper angular law

The current Kuiper family uses a 32-bit multiplicative angular mapping:

\[
\theta=
2\pi
\left(
\frac{(k\times2654435769)\bmod2^{32}}
{2^{32}}
\right)
\]

Then:

\[
x=r\cos\theta
\]

\[
y=r\sin\theta
\]

The constant 2654435769 is closely related to scaling the 32-bit range by the reciprocal of the golden ratio.

The simple golden-angle version is easier to learn first; the production form is convenient for deterministic computer arithmetic.

## Sources / further reading

- Kuiper repository: https://github.com/Ventusltd/kuiper-belt
- OpenStax, *Precalculus 2e*: https://openstax.org/details/books/precalculus-2e
- Wolfram MathWorld, Golden Ratio: https://mathworld.wolfram.com/GoldenRatio.html
