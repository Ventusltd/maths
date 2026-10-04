# Circle area: pi r squared

## The problem

We know how far a circle reaches from its centre: the **radius**.

But how much flat space is inside the circle?

That is its **area**.

## The rule

The area of a circle is:

```
pi × radius × radius
```

Usually written:

```
πr²
```

If the radius is 3 m:

```
3 × 3 = 9
9 × π ≈ 28.27
```

So the circle contains about:

```
28.27 m²
```

## Why is the radius squared?

Area is two-dimensional.

When a circle gets wider, it is expanding across both horizontal and vertical space.

That is why its area grows with the **square of the radius**.

If the radius doubles:

```
radius:  1 → 2
area:    π → 4π
```

The radius doubled, but the area became four times larger.

## Where square root comes back

Suppose we know how much area we want, but need the radius.

We can work backwards.

If:

```
area = 100π
```

then:

```
radius × radius = 100
```

so:

```
radius = √100 = 10
```

This backwards step is the reason square root becomes useful in Kuiper.

## Technical maths

Circle area:

$$
A=\pi r^2
$$

Solve for radius:

$$
\frac{A}{\pi}=r^2
$$

then:

$$
r=\sqrt{\frac{A}{\pi}}
$$

## Try it in Excel

| cell | type | expect |
|---|---|---|
| A2 | `3` (radius) | 3 |
| B2 | `=PI()*A2^2` (area) | 28.274334 |
| C2 | `=SQRT(B2/PI())` (back to radius) | 3 |

## Check it yourself

1. Radius 10: area? (314.159265)
2. Area 100π: radius? (10)
3. Radius 1 to radius 3: how many times more area? (9)

## Sources / further reading

- OpenStax, *Precalculus 2e*: https://openstax.org/details/books/precalculus-2e
