- Date: 2016-11-22

# Summary

Sometimes you need to calculate if two date ranges overlap and if so, by how much.

This may seem simple but there are five cases.


**Tl;DR;**

Given two date ranges like:

![Date Ranges](http://imgur.com/download/7UhILlt)

You can test if they overlap with:

```
NOT(B <= C OR A >= D)
```

which is equivalent to

```
(A <= D) and (B >= C)
```

You can calculate the interval that these ranges overlap by taking the minimum of:

```
[B - A, B - C, D - C, D - A]
```


# Proof

Let `conditionA` mean that date range `A` is completely after date range `B`:

![ConditionA](http://imgur.com/download/IY3xyko)

If `conditionA` is true, then `startA > endB`.

Let `conditionB` mean that date range `A` is completely before date range `B`:
![ConditionB](http://imgur.com/download/Lw1c0oF)

If `conditionB` is true, then `endA < startB`

The overlap exists if neither `conditionA` or `conditionB` is true.

So:

`NOT(conditionA OR conditionB)` <=> `NOT(conditionA) AND NOT(conditionB)`

which is equivalent to:

```
  (startA <= startB) and (endA >= startB)
```




## Resources

* See [Allens Interval Algebra](https://en.wikipedia.org/wiki/Allen%27s_interval_algebra) for the number theory.
* [Stackoverflow solution](http://stackoverflow.com/questions/325933/determine-whether-two-date-ranges-overlap)
* [Do this in 2D with rectangles](http://stackoverflow.com/questions/306316/determine-if-two-rectangles-overlap-each-other#306332)