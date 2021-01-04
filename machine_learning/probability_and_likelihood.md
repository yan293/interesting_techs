## Probability and Likelihood

### Probability
- Given distribution type (Gaussian, Gamma, Exponential), distribution parameters, the probalility number of a data.

![probability](https://latex.codecogs.com/gif.latex?p%28%5Ctext%7Bdata%7D%7C%5Ctheta_1%2C%20%5Ctheta_2%2C%20%5Ccdots%29)

- Sum to 1.


### Likelihood

- Given data, the probalility number of a guessed distribution type and distribution parameters.

![probability](https://latex.codecogs.com/gif.latex?p%28%5Ctext%7Bdata%7D%7C%5Ctheta_1%2C%20%5Ctheta_2%2C%20%5Ccdots%29)

- Not sum to 1.


### Maximizing Likelihood

Given data, figure out:
1. The distribution type (Gaussian, Gamma, Exponential, Neural Network (NN))
2. The distribution parameters (e.g. mean and std of Gaussian, the network parameters of NN)

by maximizing the number: ![probability](https://latex.codecogs.com/gif.latex?p%28%5Ctext%7Bdata%7D%7C%5Ctheta_1%2C%20%5Ctheta_2%2C%20%5Ccdots%29)

![MLE](https://latex.codecogs.com/gif.latex?%5Ctheta_1%5E*%2C%20%5Ctheta_2%5E*%2C%20%5Ccdots%20%3D%20%5Carg%20%5Cmax_%7B%5Ctheta_1%2C%20%5Ctheta_2%2C%20%5Ccdots%7D%20p%28%5Ctextbf%7Bdata%7D%7C%5Ctheta_1%2C%20%5Ctheta_2%2C%20%5Ccdots%29)
