

# Learning Probability Density Function Using Roll-Number-Parameterized Non-Linear Model
Author: Abhayjeet (102303761)

# Abstract
This assignment applies a roll-number-parameterized non-linear transformation
to NO₂ air quality data and estimates the parameters of a Gaussian-form
probability density function using Maximum Likelihood Estimation (MLE).
The transformation introduces controlled sinusoidal non-linearity based on
the university roll number, and the transformed data is modeled using
a Gaussian density function.

# Methodology

## Step 1: Transformation Parameters

r = 102303761

r mod 7 = 5
a_r = 0.05 × 5 = 0.25

r mod 5 = 1
b_r = 0.3 × (1 + 1) = 0.6

Transformation applied to NO₂ values:

z = x + 0.25 sin(0.6x)

## Step 2: Probability Density Function

The transformed variable z is modeled as:

p̂(z) = c e^(−λ (z − μ)^2)

Parameters λ, μ, and c are estimated using Maximum Likelihood
Estimation assuming Gaussian structure.

# Final Estimated Parameters

lambda = 0.001460436525489001
mu     = 25.809622897811263
c      = 0.021560876239314915

# Observations

1. The non-linear sinusoidal term introduces smooth perturbation
   to the original NO₂ values without drastic distortion.

2. The estimated μ indicates the central tendency of the
   transformed distribution around 25.81.

3. The small value of λ suggests moderate variance in the data.

4. The normalization constant c ensures that the probability
   density function integrates to 1.

# Conclusion

The transformed NO₂ data follows a Gaussian-form probability
density function characterized by the estimated parameters above.
