Probability functions
====================
Probability functions return probabilities based on various distributions, such as the probability that a value from Student's t distribution will be less than a specific value.
## Table 1. CLEM probability functions
| Function                   | Result  | Description                                                                                                                                               |
|----------------------------|---------|-----------------------------------------------------------------------------------------------------------------------------------------------------------|
| cdf_chisq(NUM, DF)         | Real    | Returns the probability that a value from the chi-square distribution with the specified degrees of freedom will be less than the specified number.       |
| cdf_f(NUM, DF1, DF2)       | Real    | Returns the probability that a value from the F distribution, with degrees of freedom DF1 and DF2, will be less than the specified number.                |
| cdf_normal(NUM, MEAN, STDDEV) | Real | Returns the probability that a value from the normal distribution with the specified mean and standard deviation will be less than the specified number.  |
| cdf_t(NUM, DF)             | Real    | Returns the probability that a value from Student's t distribution with the specified degrees of freedom will be less than the specified number.          |
