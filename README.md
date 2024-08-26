# CIR

The Cox-Ingersoll-Ross (CIR) model is a widely used interest rate model in the field of fixed income. It is particularly favored for modeling the evolution of short-term interest rates because it ensures that rates remain positive, which is a desirable property for interest rate models.


Short Rate r(t):
The short rate is the instantaneous interest rate at time t. The CIR model describes how this rate evolves over time.

Mean Reversion:
The CIR model assumes that the short rate tends to revert to a long-term average level over time. This characteristic is known as mean reversion.

Stochastic Differential Equation (SDE):
The CIR model uses a stochastic differential equation to model the short rate. The model includes both a deterministic part, which drives the mean reversion, and a stochastic part, which introduces randomness into the rate's evolution.


CIR Model Equation
The CIR model describes the evolution of the short rate r(t) using the following stochastic differential equation:
dr(t) = kappa * (theta - r(t)) * dt + sigma * sqrt(r(t)) * dW(t)
Where:
dr(t) is the change in the short rate over a small time increment dt.
kappa is the speed of mean reversion, controlling how quickly the rate reverts to its long-term mean.
theta is the long-term mean level of the short rate.
sigma is the volatility of the short rate, determining how much the rate fluctuates over time.
dW(t) is a Wiener process (standard Brownian motion), representing the random component of the rate's evolution.



Mean Reversion:
The term kappa∗(theta−r(t)) ensures that the short rate reverts to the long-term mean theta. If the short rate is above theta, the mean reversion term becomes negative, pushing the rate down. If the rate is below theta, the term becomes positive, pushing the rate up.

Non-Negativity:
The CIR model ensures that the short rate r(t) remains non-negative because the diffusion term sigma∗sqrt(r(t))∗dW(t) diminishes as r(t) approaches zero.


Bond Pricing in the CIR Model
The price P(t,T) of a zero-coupon bond maturing at time T in the CIR model can be computed using the following equation:
P(t, T) = A(t, T) * exp(-B(t, T) * r(t))
Where:
A(t,T) and B(t,T) are functions that depend on the model parameters 
kappa, theta, and sigma, as well as the time to maturity T−t.

The functions A(t,T) and B(t,T) are given by:
B(t, T) = (1 - exp(-h1 * (T - t))) / h2
A(t, T) = [h1 * exp(h2 * (T - t)) / (h2 * (exp(h1 * (T - t)) - 1) + h1)]^h3
Where:
h1 = \sqrt(kappa^{2} +2∗sigma^{2})
h2=(kappa+h1)/2
h3=2∗kappa∗theta/sigma^{2}
 

To use the CIR model for pricing bonds:
1) Simulate Short Rate Paths:
Use the CIR stochastic differential equation to simulate possible paths for the short rate over time.
2) Price Zero-Coupon Bonds:
Calculate the price of zero-coupon bonds using the bond pricing formula provided above, based on the simulated short rate paths.
