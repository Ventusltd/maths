# Which way the golden turn goes

Read [Golden ratio and golden angle](08-golden-ratio-and-golden-angle.md) first.

## The problem

Two Kuiper drawings both say "golden angle". One turns 137.5° per key. The other turns 222.5° per key.

Are they the same?

## Forward 222.5 is back 137.5

Stand facing 0°. Turn 222.5° anticlockwise.

You face the same way as if you had turned 137.5° **clockwise**.

```
222.492236° + 137.507764° = 360°
```

## So the spirals are mirror images

| drawing | step per key | winds |
|---|---|---|
| teaching sheet, Kuiper belt (`tools/estate.py`) | +137.507764° | one way |
| Kuiper wafer (`tools/wafer_keys.py`, `index.html`) | +222.492236° = -137.507764° | the other way |

Same even packing. Same arm counts. Reflected left to right.

## Key by key

| key | +137.5° sheet | wafer | 360 - sheet |
|---|---|---|---|
| 1 | 137.507764 | 222.492236 | 222.492236 |
| 2 | 275.015528 | 84.984472 | 84.984472 |
| 3 | 52.523292 | 307.476708 | 307.476708 |

The wafer column equals 360 minus the sheet column. That is a mirror.

## Why care?

If you build the spiral in Excel with 137.5° and lay it over the live wafer, it will not match. Flip it, or use 222.492236°.

## Technical maths

The two steps are $360^\circ/\varphi^2$ and $360^\circ/\varphi$, with $\varphi = 1.6180339887$.

$$
\frac{1}{\varphi} + \frac{1}{\varphi^2} = 1
$$

so the two steps add up to one full turn.

The wafer's integer constant is $2^{32}/\varphi$ rounded down, so its step is $137.507764092^\circ$ the other way, about $0.00000004^\circ$ per key away from the exact golden angle. Invisible.

## Try it in Excel

Key in A2.

| cell | type | key 1 gives |
|---|---|---|
| B2 | `=MOD(A2*137.507764,360)` | 137.507764 |
| C2 | `=MOD(A2*2654435769,2^32)/2^32*360` | 222.492236 |
| D2 | `=MOD(360-B2,360)` | 222.492236 |

Fill to key 20. C and D agree to 5 decimal places.

## Check it yourself

1. Does 137.507764 + 222.492236 make 360? (Yes)
2. Turn 270° anticlockwise. The same as how far clockwise? (90°)
3. Chart both spirals (X = `SQRT(A2)*COS(RADIANS(angle))`, Y = `SQRT(A2)*SIN(RADIANS(angle))`). Mirror images?

## Sources / further reading

- Kuiper repository: https://github.com/Ventusltd/kuiper-belt (`tools/wafer_keys.py`, `tools/estate.py`)
- Wolfram MathWorld, Golden Angle: https://mathworld.wolfram.com/GoldenAngle.html
