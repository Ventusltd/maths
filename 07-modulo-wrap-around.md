# Modulo: wrap-around arithmetic

## The problem

What should happen when an angle goes beyond one complete turn?

Suppose we reach:

```
400°
```

A full turn is 360°, so 400° points in the same direction as:

```
40°
```

We need an operation that throws away complete turns and keeps what is left.

That is the idea behind **modulo**.

## Clock example

A 12-hour clock wraps around.

```
13 o'clock → 1 o'clock
14 o'clock → 2 o'clock
25 o'clock → 1 o'clock
```

So:

```
13 mod 12 = 1
25 mod 12 = 1
```

## Circle example

```
400 mod 360 = 40
```

because:

```
400 = 360 + 40
```

Modulo keeps the remainder after complete cycles.

## Why care?

Kuiper repeatedly advances around a circle.

Modulo lets the calculation keep wrapping around rather than letting an angle grow without bound.

The same idea is common in clocks, repeating schedules, circular buffers, computer address spaces and rotations.

## Technical maths

For integers, writing:

$$
a \bmod n
$$

means the remainder associated with division by $n$, under the chosen modulo convention.

For the simple positive examples used here:

$$
400\bmod360=40
$$

and:

$$
25\bmod12=1
$$

Programming languages can differ in how they treat negative values, so implementation details matter.

## Sources / further reading

- Python numeric expressions: https://docs.python.org/3/reference/expressions.html
- MDN remainder operator: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Remainder
