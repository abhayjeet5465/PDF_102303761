
Title: Learning Probability Density Function Using Roll-Number-Parameterized Non-Linear Model

Author: Roll No. 102303761

-----------------------------------------------------------------------

ABSTRACT
This work applies a roll-number-parameterized non-linear transformation 
to NO₂ air quality data and estimates the parameters of a Gaussian-form 
probability density function using Maximum Likelihood Estimation (MLE).

-----------------------------------------------------------------------

METHODOLOGY

Step-1: Compute transformation parameters

r = 102303761

ar = 0.05 * (r mod 7) = 0.25
br = 0.3 * (r mod 5 + 1) = 0.6

Transformation:
z = x + 0.25 sin(0.6x)

Step-2: Estimate PDF parameters

p̂(z) = c * exp( -λ (z - μ)^2 )

Using MLE:
μ = mean(z)
σ² = mean((z − μ)^2)

λ = 1 / (2σ²)
c = 1 / sqrt(2πσ²)

-----------------------------------------------------------------------

IMPLEMENTATION (Google Colab Compatible)

import numpy as np
import pandas as pd

r = 102303761

ar = 0.05 * (r % 7)
br = 0.3 * ((r % 5) + 1)

df = pd.read_csv('/content/india_air_quality_data.csv')

x = df['NO2'].dropna().values
z = x + ar * np.sin(br * x)

mu = np.mean(z)
sigma2 = np.mean((z - mu)**2)

lam = 1 / (2 * sigma2)
c = 1 / np.sqrt(2 * np.pi * sigma2)

print("lambda =", lam)
print("mu =", mu)
print("c =", c)

-----------------------------------------------------------------------

FINAL OUTPUT

lambda = 0.001460436525489001
mu     = 25.809622897811263
c      = 0.021560876239314915

-----------------------------------------------------------------------

CONCLUSION

The transformed NO₂ values follow a Gaussian-form probability density 
function with the above estimated parameters obtained using MLE.

