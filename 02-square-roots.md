# Square roots

## The problem

Suppose a square piece of land has an area of **100 m²**.

How long is each side?

You need the number that multiplies by itself to make 100.

```
10 × 10 = 100
```

So each side is 10 m.

Square root is the operation that asks that question.

## What a square root means

> What number, multiplied by itself, gives the number I started with?

Examples:

```
√9 = 3      because 3 × 3 = 9
√16 = 4     because 4 × 4 = 16
√25 = 5     because 5 × 5 = 25
√100 = 10   because 10 × 10 = 100
```

So square root is the inverse operation of squaring.

## What about √10?

There is no whole number that multiplies by itself to make exactly 10.

```
3 × 3 = 9
4 × 4 = 16
```

So the answer must lie between 3 and 4.

It begins:

```
√10 = 3.162277660168379...
```

The decimal continues forever without repeating.

A calculator shows a rounded approximation.

## Why care?

Square root lets us work backwards from an area-like quantity to a length-like quantity.

That becomes important later in circles and in Kuiper.

## Technical maths

If:

$$
b^2=a
$$

then:

$$
\sqrt{a}=b
$$

For positive real numbers, $\sqrt{a}$ means the non-negative square root.

For example:

$$
(\sqrt{10})^2=10
$$

The number $\sqrt{10}$ is irrational, meaning it cannot be written exactly as a ratio of two integers.

## Try it in Excel

| cell | type | expect |
|---|---|---|
| A2 | `10` | 10 |
| B2 | `=SQRT(A2)` | 3.16227766 |
| C2 | `=B2*B2` | 10 |

C2 squares the answer back. That is how to check any square root.

## Check it yourself

1. √49? (7)
2. √50 lies between which two whole numbers? (7 and 8)
3. Square 3.162 by hand or calculator. Is it just under 10? (9.998244)

## Sources / further reading

- OpenStax, *Prealgebra 2e*: https://openstax.org/details/books/prealgebra-2e
- NIST Digital Library of Mathematical Functions: https://dlmf.nist.gov/
