# 01.Propagating-Uncertainty-in-Dynamical-Systems

This experiment evaluates GP-LSTM's (Gaussian Process regression in combination with LSTM's) on their ability to forecast the predictive distribution of dynamical systems.
The GP-LSTM models are built using the keras-gp library (https://github.com/alshedivat/keras-gp) with an octave engine.

*01.01 One Dimensional Random Walk*

The variance estimates of the GP-LSTM model are evaluated on a simple one
dimensional random walk. The data is generated by sampling a random step
from a normal distribution with mean 0 and variance $σ^2$.
The GP-LSTM is trained for one-step-ahead predictions using a random walk with 1000 time steps.

An uncertainty propagation algorithm is applied to propagate predictive uncertainties n-steps into the future.

