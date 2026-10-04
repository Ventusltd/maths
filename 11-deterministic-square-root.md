# How a calculator finds a square root

## The problem

A calculator is not born knowing every square root.

It needs a repeatable recipe.

For example, to find the square root of 10, it needs to find a number which multiplied by itself is extremely close to 10.

## A simple deterministic recipe

Start with a rough guess.

For √10, choose 3.

Then repeat:

1. divide 10 by the current guess;
2. average that answer with the current guess;
3. use the average as the new guess.

Example:

```
guess = 3
10 ÷ 3 = 3.333333...
average of 3 and 3.333333... = 3.166666...
```

Repeat:

```
10 ÷ 3.166666... ≈ 3.157894...
average ≈ 3.162280...
```

Repeat again and the value quickly settles near:

```
3.162277660168379...
```

## Why the correction works

If the guess is too low, dividing the target by that guess produces a partner that is too high.

For 10:

```
guess = 3
10 ÷ 3 = 3.333...
```

One number is below the true square root and the other is above it.

Averaging them gives a better estimate.

The process repeats until the stored answer is precise enough for the machine.

## What "deterministic" means

The calculator is not improvising.

The same input and the same algorithm produce the same sequence of operations.

A computer can implement the recipe using basic operations such as load, divide, add, divide by 2, compare, store and repeat.

At the electrical level, processor circuits built from transistors carry out those instructions on binary numbers.

## Technical maths

The classical Babylonian / Heron iteration for $\sqrt{S}$ is:

$$
g_{n+1}=\frac12\left(g_n+\frac{S}{g_n}\right)
$$

For positive $S$ and a suitable positive starting guess, the sequence converges rapidly to:

$$
\sqrt{S}
$$

This is also a special case of Newton's method applied to:

$$
f(g)=g^2-S
$$

## Try it in Excel

| cell | type | expect |
|---|---|---|
| A2 | `3` (first guess) | 3 |
| A3 | `=(A2+10/A2)/2` | 3.166666667 |
| A4 | fill down | 3.162280702 |
| A5 | fill down | 3.162277660 |
| A6 | fill down | 3.162277660 |

Four steps and it has stopped changing. Compare with `=SQRT(10)`.

## Check it yourself

1. Start at 3 for √9. What happens? (It stays at 3: already right)
2. Start at 1 for √10. How many steps to settle? (About 6)
3. Run it for √2 starting at 1. (1.5, 1.416667, 1.414216, 1.414214)

## Sources / further reading

- Encyclopaedia Britannica, Newton's method: https://www.britannica.com/science/Newtons-method
- NIST Digital Library of Mathematical Functions: https://dlmf.nist.gov/
