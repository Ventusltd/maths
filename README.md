# Maths from first principles

Practice of mathematical ideas used in globalgrid2050.com, especially the Kuiper grid, but useful well beyond it.

This repository explains maths **problem first, intuition second, formula last**.

Each note follows the same pattern:

1. What problem are we trying to solve?
2. What does it mean in ordinary language?
3. A small worked example
4. Why it matters
5. Technical maths near the bottom
6. Try it in Excel: exact formulas and the values to expect
7. Check it yourself: three questions with answers
8. Sources / further reading

The aim is not to memorise symbols before they have meaning.

## Learning path

0. [Fractions and decimals](00-fractions-and-decimals.md) (start here if "0.618 of a turn" is new)
1. [Squaring](01-squaring.md)
2. [Square roots](02-square-roots.md)
3. [Area and square units](03-area-and-square-units.md)
4. [Circles, radius, diameter and pi](04-circles-radius-diameter-pi.md)
5. [Circle area: pi r squared](05-circle-area-pi-r-squared.md)
6. [Angles and turns](06-angles-and-turns.md)
7. [Modulo: wrap-around arithmetic](07-modulo-wrap-around.md)
   - 7a. [Powers of two and the 32-bit odometer](07a-powers-of-two-and-the-32-bit-odometer.md)
8. [Golden ratio and golden angle](08-golden-ratio-and-golden-angle.md)
   - 8a. [Which way the golden turn goes](08a-which-way-the-golden-turn-goes.md)
9. [Coordinates, sine and cosine](09-coordinates-sine-cosine.md)
10. [Kuiper placement law](10-kuiper-placement-law.md)
11. [How a calculator finds a square root](11-deterministic-square-root.md)

## The real Kuiper in one box

```
radius = SQRT(key)
         (live view: SQRT(key + 0.5), keys from 0)
angle  = 0.6180339887 of a turn per key = 222.492236 degrees
         (the golden angle 137.5 degrees, turned the other way)
area inside key k = pi x k, exactly
```

## Rule for reading

If a symbol looks meaningless, stop and go back to the physical problem it is describing.

The formal maths is deliberately placed near the bottom of each file rather than at the beginning.

## Public diary

- [5 October 2026: Learn the Kuiper and connected projects](diary/2026-10-05-learn-the-kuiper.md)
- [Public project links and source revisions](https://github.com/Ventusltd/kuiper-belt/blob/main/diary/2026-10-05-public-links.json)
