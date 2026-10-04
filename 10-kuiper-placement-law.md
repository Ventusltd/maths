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

Using square root makes the area grow **exactly** in step with the number of keys: every key owns π square units. Not roughly. Exactly.

## Step 2: direction

Use an angular rule that keeps wrapping around the circle and avoids simple repeating spokes.

A teaching version is:

```
angle = (key × 137.507764°) mod 360°
```

Warning: the deployed wafer turns the other way, 222.492236° per key. See Step 2 in production, below.

## Step 3: convert to X and Y

```
X = radius × cosine(angle)
Y = radius × sine(angle)
```

Now every key can generate a coordinate.

No individual coordinate needs to be typed by hand.

## Why the square root is important

For key $k$:

$$
r=\sqrt{k}
$$

Circle area is:

$$
A=\pi r^2
$$

Substitute $r=\sqrt{k}$:

$$
A=\pi(\sqrt{k})^2
$$

so:

$$
A=\pi k
$$

That is the important result.

As the key count grows, the available area grows in exact proportion. The ring between key $k$ and key $k+1$ has area $\pi(k+1)-\pi k=\pi$, whatever $k$ is.

## Production Kuiper angular law

The current Kuiper family uses a 32-bit multiplicative angular mapping:

$$
\theta=
2\pi
\left(
\frac{(k\times2654435769)\bmod2^{32}}
{2^{32}}
\right)
$$

Then:

$$
x=r\cos\theta
$$

$$
y=r\sin\theta
$$

The constant 2654435769 is $2^{32}/\varphi = 2654435769.497...$ rounded down (hex `9E3779B9`). So one key moves the angle on by 0.6180339887 of a turn, **222.492236°**. That is the golden angle 137.507764° turned the other way: a mirror image. See [Which way the golden turn goes](08a-which-way-the-golden-turn-goes.md).

## What the live page actually draws

The data law (`tools/wafer_keys.py` line 80) is $r=\sqrt{k}$.

The live view (`index.html` lines 144 to 147 and 250) counts keys from 0 and draws:

$$
r=\sqrt{k+0.5}
$$

Why the extra half? Key $k$ owns the ring from $\sqrt{k}$ to $\sqrt{k+1}$. Adding 0.5 puts the dot in the middle of its ring, and stops key 0 sitting exactly on the centre.

| key | angle (°) | data radius $\sqrt{k}$ | drawn radius $\sqrt{k+0.5}$ |
|---|---|---|---|
| 0 | 0 | 0 | 0.707107 |
| 1 | 222.492236 | 1 | 1.224745 |
| 2 | 84.984472 | 1.414214 | 1.581139 |
| 3 | 307.476708 | 1.732051 | 1.870829 |

The Kuiper belt of repositories (`tools/estate.py` lines 157 to 158) uses the same idea scaled to fit: $r = R\sqrt{(k+0.5)/n}$ and $+137.5^\circ$ per body.

## Try it in Excel

Key in A2 (start at 1). Then:

| cell | formula | key 1 gives |
|---|---|---|
| B2 | `=SQRT(A2)` | 1 |
| C2 | `=MOD(A2*2654435769,4294967296)` | 2654435769 |
| D2 | `=C2/4294967296*360` | 222.492236 |
| E2 | `=B2*COS(RADIANS(D2))` | -0.737369 |
| F2 | `=B2*SIN(RADIANS(D2))` | -0.675490 |

Fill down. Key 2 gives D = 84.984472.

**Excel's limit.** Excel holds whole numbers exactly only up to $2^{53}$ = 9,007,199,254,740,992. `A2*2654435769` goes past that above key 3,393,263, and C2 quietly goes wrong. The real wafer has 43,486,619,138 issued keys, so for big keys use the split formula, which never goes past $2^{53}$:

```
=MOD(MOD(MOD(A2,4294967296)*40503,65536)*65536+MOD(A2,4294967296)*31161,4294967296)
```

It works because 2654435769 = 40503 × 65536 + 31161. For key 43486619138 it gives **305752434**; the plain formula gives a wrong number.

## Check it yourself

1. Key 9: radius 3? Area inside it $\pi	imes 9 = 28.274334$?
2. Key 2's angle: 2 × 222.492236 = 444.984472, minus 360 = 84.984472. Does D3 agree?
3. `=360-D2` for key 1: 137.507764, the golden angle. Mirror confirmed.

## Sources / further reading

- Kuiper repository: https://github.com/Ventusltd/kuiper-belt
- OpenStax, *Precalculus 2e*: https://openstax.org/details/books/precalculus-2e
- Wolfram MathWorld, Golden Ratio: https://mathworld.wolfram.com/GoldenRatio.html
