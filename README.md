# 01.Propagating-Uncertainty-in-Dynamical-Systems

This experiment evaluates GP-LSTM's (Gaussian Process regression in combination with LSTM's) on their ability to forecast the predictive distribution of dynamical systems.
The GP-LSTM models are built using the keras-gp library (https://github.com/alshedivat/keras-gp) with an octave engine.

*01.01 One Dimensional Random Walk*

The predictive distributions of the GP-LSTM model are evaluated on a simple one
dimensional random walk. The data is generated by sampling a random step
from a normal distribution with mean 0 and variance <img src="https://render.githubusercontent.com/render/math?math=\sigma^{2}">.

The GP-LSTM is trained for one-step-ahead predictions using a random walk with 1000 time steps.
An uncertainty propagation algorithm is applied to propagate predictive uncertainties 10 steps into the future by sampling a given number of samples per time step using the predicted distribution.
The results from one experiment are shown below:

<img src="./Figures/RW_uncertainty_propagated_resized.jpg" width="350" height="300" />

The evaluation of the predicted distributions is based on the square root of time rule.
According to the square root of time rule for simple random walks, the variance for a n-th step ahead prediction <img src="https://render.githubusercontent.com/render/math?math=\sigma_{n}^{2}">
is the sum of the variances of each
individual taken step and hence <img src="https://render.githubusercontent.com/render/math?math=n*\sigma_{1}^{2}">. 
In other words, variances are added if independent and identically distributed random variables are added.
[A proof of method can be found here](ProofofMethods/Cumulative_Variances.pdf)