# StableMarriage

The Stable Marriage Problem states that given N men and N women, where each person has ranked all members of the opposite sex in order of preference, marry the men and women together such that there are no two people of opposite sex who would both rather have each other than their current partners. If there are no such people, all the marriages are “stable”

This code will check if a current marriage is stable based on the following conditions

a. if the current man prefers the new woman to his partner and
b. if the new woman prefers the current man to her partner
  i. this is unstable, so return false
c. if the new man prefers the current woman to his partner and
d. if the current woman prefers the new man to her partner
  i. This is unstable, so return false
e. if there are no instabilities introduced with any of the existing (i.e. “current”)
couples, so we return true
