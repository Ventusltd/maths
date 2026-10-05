# Powers of two and the 32-bit odometer

Read [Modulo](07-modulo-wrap-around.md) first.

## The problem

Kuiper's angle law contains the number $2^{32}$ = 4,294,967,296.

Where does such an odd number come from, and why does it behave like a circle?

## Doubling

Start at 1 and keep doubling:

```
2^1 = 2
2^2 = 4
2^3 = 8
2^8 = 256
2^16 = 65,536
2^32 = 4,294,967,296
```

$2^{32}$ means "32 twos multiplied together".

## Why computers like it

A computer stores whole numbers in switches that are on or off. 32 switches can show $2^{32}$ different patterns: the numbers 0 to 4,294,967,295.

## The odometer

A car's mileage counter with 2 digits shows 00 to 99. Add 1 to 99 and it rolls over to 00.

That is modulo 100.

A 32-bit counter is the same thing with a bigger dial. Go past 4,294,967,295 and it rolls back to 0. That is modulo $2^{32}$.

Because it rolls round, the dial behaves like a **circle**: 0 to $2^{32}$ is one full turn.

## Kuiper's step

On a 2-digit odometer, step by 62 each time. 62/100 is close to 0.618, the golden fraction. The readings scatter evenly:

```
00, 62, 24, 86, 48, 10, 72, 34, ...
```

Kuiper does the same on the 32-bit dial with the step

```
2654435769  ≈  4294967296 × 0.6180339887
```

Key 1 sits at 2,654,435,769 on the dial. Key 2 at 5,308,871,538, which rolls over to 1,013,904,242.

Divide the dial reading by $2^{32}$ to get the fraction of a turn.

## Why care?

A graphics card multiplies 32-bit numbers and rolls them over for free. So the angle is exact and identical on every machine.

## Technical maths

$$
m = (k \times 2654435769) \bmod 2^{32}, \qquad \theta = 2\pi \frac{m}{2^{32}}
$$

## Try it in Excel

| cell | type | expect |
|---|---|---|
| A2 | `=2^32` | 4294967296 |
| B2 | `=MOD(2*2654435769,2^32)` | 1013904242 |
| C2 | `=B2/2^32*360` | 84.984472 |

Excel only holds whole numbers exactly up to $2^{53}$, so the plain formula goes wrong above key 3,393,263. For big keys use the split formula in [note 10](10-kuiper-placement-law.md).

## Check it yourself

1. $2^{10}$? (1024)
2. On a 2-digit odometer, 85 + 30 shows? (15)
3. Step 62 on the 2-digit odometer: the reading after 34? (96)

## Sources / further reading

- OpenStax, *Prealgebra 2e*, exponents: https://openstax.org/details/books/prealgebra-2e
- D. E. Knuth, *The Art of Computer Programming*, Vol. 3, section 6.4 (multiplicative hashing, the 2654435769 constant)
