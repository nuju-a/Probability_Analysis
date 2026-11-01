## Findings(Put together with the help of claude.ai)

## State Organic Livestock
All 50 states match the raw file on region, 2008 values, raw 2011 values and raw totals. The clean 2011 totals reconcile to the U.S. row.
The South's large rise is driven mainly by Texas (+36,607). The South total also includes Arkansas and Georgia as zeros in 2011.
Largest state increases: Texas +36,607, Wisconsin +10,708, Minnesota +7,484, Pennsylvania +4,935. Largest decreases: Oregon -10,528, New Mexico -9,029, Nebraska -7,984, Washington -7,470.
26 states increased, 21 decreased and 3 were unchanged (all three at zero).

# Tiers 
(Tier 1 at 20,000 or more, Tier 2 at 5,000 or more, Tier 3 at 1 or more): in 2011 there are 8 Tier 1 states (California, Texas, Wisconsin, New York, Oregon, Pennsylvania, Vermont, Minnesota), 11 Tier 2, 27 Tier 3 and 4 with None.
Twelve states have a 2011 total above 10,000: California, Colorado, Iowa, Minnesota, New York, Ohio, Oregon, Pennsylvania, Texas, Vermont, Washington, Wisconsin.



## Checks (tab: empirical prob. solution sheet)

`=SKEW(J9:J58)`
Action: computes the sample skewness of 2011 milk cows across the 50 states.

`=AVERAGE(J9:J58)-MEDIAN(J9:J58)`
Action: subtracts the median from the mean of 2011 milk cows.

`=SKEW(N9:N58)`
Action: computes the sample skewness of the clean 2011 totals.

`=MAX(J9:J58)/SUM(J9:J58)`
Action: divides the largest state's milk cows by the 50-state total

`=COUNTIFS(K9:K58,">=1000",K9:K58,"<=10000")/COUNTA(A9:A58)`
Action: counts states whose clean 2011 milk cows are at least 1,000 and at most 10,000, then divides by the number of states.

Excluding the four no-data states changes the denominator to 46: P(total > 10,000) becomes 12/46 = 0.261 and P(milk inclusive) becomes 13/46 = 0.283. P(West) is unaffected, because every state has a region.

The 13 mid-size milk states are Idaho, Illinois, Indiana, Iowa, Kentucky, Maine, Maryland, Michigan, Missouri, New Mexico, Ohio, Virginia and Washington.

**

## Empirical probabilities

Calculated on the empirical prob. solution sheet (see the Sheet link in the README). Denominator is 50 states, clean 2011 columns (blanks = 0). P(West) = 0.26, P(2011 total > 10,000) = 0.24, P(2011 milk 1,000 to 10,000 inclusive) = 0.26.

`=COUNTIFS(K9:K58,">=1000",K9:K58,"<=10000")/COUNTA(A9:A58)`

Action: counts states whose clean 2011 milk cows are at least 1,000 and at most 10,000, then divides by the number of states.

Excluding the four no-data states changes the denominator to 46: P(total > 10,000) becomes 12/46 = 0.261 and P(milk inclusive) becomes 13/46 = 0.283. P(West) is unaffected, because every state has a region.

The 13 mid-size milk states are Idaho, Illinois, Indiana, Iowa, Kentucky, Maine, Maryland, Michigan, Missouri, New Mexico, Ohio, Virginia and Washington.

**

## Mastersheet

A static summary of states, climate zone, tier in each year, tier change and a mid-size dairy flag. Every row agrees with the State sheet.

* Tier changes: 43 states unchanged, 5 up (Alabama, Florida, Minnesota, Nevada, South Carolina), 2 down (Arkansas, Nebraska). Arkansas's drop is an artefact of missing 2011 data, not a real decline.
* Mid-size dairy states (1,000 to 10,000 milk cows in 2011): 13 states.

The totals count milk cows, not farms. States with more than 10,000 milk cows (for example California at 57,809) are outside this band by design.

## Livestock and Subsidies

Subsidised number = U.S. total x subsidy rate (1.2% in 2008, 2.5% in 2011). Cost = subsidised number x average price per animal.

Cost rose 140.6%. Three things drive it: the subsidy rate more than doubled (1.2% to 2.5%), prices rose between 10% and 21%, and the animal count grew 3.5%.
Milk cows are 68.2% of the 2008 cost and 67.0% of the 2011 cost. Beef cows rose from 9.2% to 16.0% of the cost, and other cows fell from 22.0% to 16.4%.
Assumptions: the same rate applies to every livestock type, prices are the given averages, and subsidised "numbers" are fractional because they are not rounded.

## Certifiers

59 certifying bodies (data rows 4 to 62). The "U.S. Total" row is excluded from every count.

Status: 48 active and 11 inactive (9 surrendered and 2 revoked). These 11 bodies held 32 producers in 2011.
Headquarters region: West 23, Midwest 14, South 11, Northeast 11.
Producers certified: 12,744 (2008) and 12,742 (2011), essentially flat. By headquarters region: West 5,133 to 4,811, Midwest 4,158 to 4,291, South 782 to 921, Northeast 2,671 to 2,719.
Individual changes: 31 bodies grew, 21 declined and 7 were unchanged. Largest gains: Organic Certifiers, Inc. (+343), Midwest Organic Services Association, Inc. (+232), Kentucky Dept. of Agriculture (+189). Largest losses: Guaranteed Organic Certification Agency (-384), Mofga Certification Services (-235), Quality Assurance International (-235).
Concentration: the five largest bodies certified 40.6% of 2011 producers. The largest has 1,782.
Accreditation year: 45 of 59 bodies were accredited in 2002; the others in 2003 (4), 2006 (4), 2004 (2), 2007 (2) and 2009 (2).
Growth is shown as "No data" for 10 bodies with no 2008 producers.
The Ecocert ICO bracket "(Indiana Certified Organic)" is part of its name, not a status. It is counted as active.

## Charts

Differences in totals (2011 minus 2008 totals, 50 states): 37 states sit in the central bar. The tails run from -10,528 (Oregon) to +36,607 (Texas), which shows the right skew.
## Why the skew
Counts have a floor at zero but no ceiling, and a few states are very large. California holds about 22.7% of milk cows and about 16.6% of total livestock. The three largest totals are California (81,831), Texas (76,142) and Wisconsin (62,235).

Milk cow distribution, 2011: 37 states have 5,000 or fewer milk cows. One state (California, 57,809) sits alone at the far right.
Total livestock distribution, 2011: 38 states have 10,000 or fewer animals. Wisconsin, Texas and California each sit alone in the 60,000 to 90,000 range.

## Random sampling

Population mean (50 states) = 9,847.06. Three random samples of states, drawn without replacement:

Each result is a single random draw, so the sample means are not guaranteed to move closer to the population mean as n grows (the 35-state mean is further away than the 25-state mean).

The 10-state sample missed the large states, so its mean and interval sit well below the population mean. With skewed data and a small sample, a 95% interval can miss the true mean.

Method: margins use z = 1.96 with each sample's own standard deviation (normal approximation) and no finite-population correction.

**

## Independent sample t-test (West vs South, 2011 totals)

H₀: the population mean 2011 total is the same in West and South states. Hₐ: it differs. Pooled (equal-variance) test, α = 0.05. Pooled SD 20,356.6, df = 27, t = 0.900, critical value ±2.052, p = 0.376. Decision: fail to reject H₀.

The sample means are dominated by a few large states (California 81,831 in the West; Texas 76,142 in the South), so the equal-means test has little power here.

Excluding the 4 no-data states (West n = 12, South n = 14): means 13,412 and 6,329, t = 0.843, p = 0.408.

**

## Paired t-test (2008 vs 2011 state totals)

H₀: the mean difference (2011 minus 2008) in a state's total is 0. Hₐ: it is not 0. Two-tailed, α = 0.05, n = 50 states.

Decision: |t| is below the critical value and p is above 0.05, so we fail to reject H₀. There is no evidence that the average state total changed.

Excluding the 4 no-data states (n = 46): mean difference 381.9, t = 0.390, p = 0.698. Same conclusion.

Normality: the differences are strongly right-skewed (skew 3.76), driven by a few states (Texas +36,607, Wisconsin +10,708, Oregon -10,528). The mean difference (330) is far above the median (42).

**

## Caveats

2011 zeros for Alaska, Arkansas, Connecticut and Georgia mean "no data", not "no livestock". Regional and tier-change results include them as zeros.
State totals are heavily right-skewed, so means reflect a few large states. Medians give a fuller picture.
All tests treat the 50 states as the sample, and all findings describe association, not cause.
Prices and subsidy rates are given inputs, not derived from the data.
