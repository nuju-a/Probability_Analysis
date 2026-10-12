 Findings

## 2011 milk cow distribution
50 states, clean column J, blanks = 0, U.S. total row excluded, bin size 5,000.

The histogram is strongly right-skewed. Bin counts from the lowest bin: `37 | 4 | 4 | 1 | 1 | 1 | 1 | 0 | 0 | 0 | 0 | 1`. 37 states fall in the first bin (0 to 5,000) and only California (57,809) sits in the last bin (55,000 to 60,000). The mean (5,095.42) is 4,388.92 above the median (706.5), and the sample skewness is about 3.32. 10 states have 0 milk cows.

## 2011 total livestock
50 states, clean column N, blanks = 0, bin size 10,000.

Bin counts: `38 | 4 | 4 | 1 | 0 | 0 | 1 | 1 | 1`. The mean (9,847.06) is 7,660.56 above the median (2,186.5), and the skewness is about 2.83. Milk cows are the largest component (about 52% of the 492,353 total), so the total has the same right-skewed shape. Excluding the 4 no-data states (46 states): mean about 10,703, median about 2,515, skewness about 2.70, so the conclusion is unchanged.

## Why the skew
Counts have a floor at zero but no ceiling, and a few states are very large. California holds about 22.7% of milk cows and about 16.6% of total livestock. The three largest totals are California (81,831), Texas (76,142) and Wisconsin (62,235).

## Checks (tab: empirical prob. solution sheet)

`=SKEW(J9:J58)`
Action: computes the sample skewness of 2011 milk cows across the 50 states.

`=AVERAGE(J9:J58)-MEDIAN(J9:J58)`
Action: subtracts the median from the mean of 2011 milk cows.

`=SKEW(N9:N58)`
Action: computes the sample skewness of the clean 2011 totals.

`=MAX(J9:J58)/SUM(J9:J58)`
Action: divides the largest state's milk cows by the 50-state total
## Empirical probabilities
Calculated on the empirical prob. solution sheet (see the Sheet link in the README). Denominator is 50 states, clean 2011 columns (blanks = 0). P(West) = 0.26, P(2011 total > 10,000) = 0.24, P(2011 milk 1,000 to 10,000 inclusive) = 0.26.