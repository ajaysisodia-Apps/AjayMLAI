**Context**

Imagine driving through town and a coupon is delivered to your cell phone for a restaurant near where you are driving. Would you accept that coupon and take a short detour to the restaurant? Would you accept the coupon but use it on a subsequent trip? Would you ignore the coupon entirely? What if the coupon was for a bar instead of a restaurant? What about a coffee house? Would you accept a bar coupon with a minor passenger in the car? What about if it was just you and your partner in the car? Would weather impact the rate of acceptance? What about the time of day?

Obviously, proximity to the business is a factor on whether the coupon is delivered to the driver or not, but what are the factors that determine whether a driver accepts the coupon once it is delivered to them? How would you determine whether a driver is likely to accept a coupon?

**Overview**

The goal of this project is to use visualizations and probability distributions to distinguish between customers who accepted a driving coupon versus those that did not.

**Data**

This data comes to us from the UCI Machine Learning repository and was collected via a survey on Amazon Mechanical Turk. The survey describes different driving scenarios including the destination, current time, weather, passenger, etc., and then ask the person whether he will accept the coupon if he is the driver. Answers that the user will drive there ‘right away’ or ‘later before the coupon expires’ are labeled as ‘Y = 1’ and answers ‘no, I do not want the coupon’ are labeled as ‘Y = 0’.  There are five different types of coupons -- less expensive restaurants (under \$20), coffee houses, carry out & take away, bar, and more expensive restaurants (\$20 - $50).

**Findings**
The dataset includes more entries from warmer temperatures, and the histograms show that coupon acceptance generally increases as temperatures rise.

For Bar coupons, the overall acceptance rate is 41%. The bigger insight comes from bar‑visiting habits: drivers who go three times or less per month accept at 37.1%, while those who go more than three times per month accept at 76.8%. That’s a major jump.

Drivers over 25 who also visit bars more than once a month have a 69.5% acceptance rate, compared to 33.5% for everyone else. This lower rate makes sense because the “other” group includes younger drivers—some possibly under the legal drinking age—and people who don’t go to bars at all.

The data also shows that drivers under 30 who visit bars more than once a month tend to accept coupons at a high rate. Another small pattern is that parents traveling without a child are more likely to accept Bar coupons.
I also ran some additional analysis. Companion type and gender by themselves don’t seem to have much impact on acceptance rates. 
Carry‑out and take‑away coupons, however, have the highest acceptance regardless of marital status. 
Coupons with a one‑day expiration are accepted more often. On sunny days, overall acceptance is higher—which fits intuition—but an interesting detail is that cheaper restaurant coupons see the highest acceptance specifically on sunny days.
