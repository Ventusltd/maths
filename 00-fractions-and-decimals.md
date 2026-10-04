# Fractions and decimals

Start here if "0.618 of a turn" means nothing yet.

## The problem

Kuiper keeps talking about *part* of something: part of a turn, part of a range.

We need a way to write "part of a whole".

## A fraction is a sharing

Cut a pizza into 4 equal slices and take 1.

You have:

```
1/4   (one quarter)
```

The bottom number says how many equal pieces. The top number says how many you took.

```
3/4 = three of the four pieces
```

## A decimal is the same thing, written in tenths

Divide the top by the bottom:

```
1 ÷ 4 = 0.25
3 ÷ 4 = 0.75
1 ÷ 2 = 0.5
```

So 0.25 and 1/4 are the same amount.

## Part of a turn

A full turn is 360°.

```
0.25 of a turn = 0.25 × 360 = 90°
0.5  of a turn = 0.5  × 360 = 180°
```

Kuiper's wafer moves each key on by 0.6180339887 of a turn:

```
0.6180339887 × 360 = 222.492236°
```

## The whole-number part and the leftover part

```
2.75 = 2 whole turns + 0.75 of a turn
```

Only the leftover, 0.75, decides the direction. Two whole turns bring you back where you started.

The leftover part is called the **fractional part**. Kuiper's law writes it as `frac`.

## Technical maths

$$
\frac{a}{b} = a \div b
$$

The fractional part of $x$ is

$$
\operatorname{frac}(x) = x - \lfloor x \rfloor
$$

where $\lfloor x \rfloor$ means "round down to a whole number".

## Try it in Excel

| cell | type | expect |
|---|---|---|
| A2 | `=3/4` | 0.75 |
| B2 | `=0.25*360` | 90 |
| C2 | `=2.75-INT(2.75)` | 0.75 |
| D2 | `=MOD(2.75,1)` | 0.75 |

## Check it yourself

1. 1/8 as a decimal? (0.125)
2. 0.1 of a turn in degrees? (36)
3. Fractional part of 5.3? (0.3)

## Sources / further reading

- OpenStax, *Prealgebra 2e*, chapters on fractions and decimals: https://openstax.org/details/books/prealgebra-2e
