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

The deployed Kuiper wafer does **not** turn 137.5° per key.

It turns 0.6180339887 of a turn per key, which is **222.492236°**.

```
222.492236° + 137.507764° = 360°
```

So the wafer is the golden spiral seen in a mirror: the same packing, wound the other way.

The teaching version (and the Kuiper belt in `tools/estate.py`) turns 137.5° one way; the wafer turns 137.5° the other way. Both are good. They are not the same picture.

See [Which way the golden turn goes](08a-which-way-the-golden-turn-goes.md).

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

The complementary rotation $360^\circ/\varphi \approx 222.492236^\circ$ gives the mirror image: the same spacing, wound the opposite way. This is the one the Kuiper wafer uses.

## Try it in Excel

| cell | type | expect |
|---|---|---|
| A2 | `=(1+SQRT(5))/2` | 1.618034 |
| B2 | `=1/A2` | 0.618034 |
| C2 | `=360*B2` | 222.492236 |
| D2 | `=360-C2` | 137.507764 |

## Check it yourself

1. Is B2 the same as A2 - 1? (Yes: 0.618034)
2. Does C2 + D2 make 360? (Yes)
3. Key 1 on the wafer: 222.49° or 137.51°? (222.49°)

## Sources / further reading

- Encyclopaedia Britannica, Golden ratio: https://www.britannica.com/science/golden-ratio
- Wolfram MathWorld, Golden Ratio: https://mathworld.wolfram.com/GoldenRatio.html
