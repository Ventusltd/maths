# Golden ratio and golden angle

## The problem

Suppose we keep placing points around a circle.

If we rotate by a simple fraction of a turn, the points soon line up.

For example, rotating by 90° gives:

```
0°, 90°, 180°, 270°, 0°, 90°...
```

Only four directions are used.

That creates obvious spokes.

We want a step that does not divide neatly into a full turn.

## The golden ratio

The golden ratio is approximately:

```
1.6180339887...
```

Its reciprocal is approximately:

```
0.6180339887...
```

That fraction of a full 360° turn is about:

```
222.492°
```

Going forward 222.492° is equivalent to going backward:

```
360° - 222.492° = 137.508°
```

That smaller angle is called the **golden angle**.

## Why is it useful?

Because the golden ratio is irrational, the step does not settle into a simple repeating fraction of a turn.

Successive points keep falling into different angular gaps instead of repeatedly using a few spokes.

This is why golden-angle-like arrangements are useful for distributing points.

## Kuiper connection

A simple teaching version can use:

```
angle = (key × 137.507764°) mod 360°
```

The production Kuiper law uses a computer-friendly 32-bit multiplicative form of the same spreading idea.

## Technical maths

Golden ratio:

$$
\varphi=\frac{1+\sqrt5}{2}\approx1.6180339887
$$

Reciprocal:

$$
\frac1\varphi=\varphi-1\approx0.6180339887
$$

Golden angle:

$$
360^\circ\left(1-\frac1\varphi\right)
\approx137.507764^\circ
$$

An equivalent complementary rotation is about $222.492236^\circ$.

## Sources / further reading

- Encyclopaedia Britannica, Golden ratio: https://www.britannica.com/science/golden-ratio
- Wolfram MathWorld, Golden Ratio: https://mathworld.wolfram.com/GoldenRatio.html
