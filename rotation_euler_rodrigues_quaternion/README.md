# Rotation Representations

In general, there are 4 different representations of rotation: (1) Rotation matrix; (2) Euler rotation angles; (3) Rodrigues vector; (4) Quaternion.  Each of the four representations has pros and cons.

The blog gives a brief summary of the 4 rotation representation methods and their pros and cons.

\mathbf{R} = \begin{bmatrix}
r_{11} & r_{12} & r_{13} \\
r_{21} & r_{22} & r_{23} \\
r_{31} & r_{32} & r_{33}
\end{bmatrix} = \begin{bmatrix}
\mathbf{r_{1}} & \mathbf{r_{2}} & \mathbf{r_{3}}
\end{bmatrix}


<!------------------------------------------------>

## 1. Rotation Matrix

![eq:rot_mat](https://latex.codecogs.com/gif.latex?%5Cmathbf%7BR%7D%20%3D%20%5Cbegin%7Bbmatrix%7D%20r_%7B11%7D%20%26%20r_%7B12%7D%20%26%20r_%7B13%7D%20%5C%5C%20r_%7B21%7D%20%26%20r_%7B22%7D%20%26%20r_%7B23%7D%20%5C%5C%20r_%7B31%7D%20%26%20r_%7B32%7D%20%26%20r_%7B33%7D%20%5Cend%7Bbmatrix%7D%20%3D%20%5Cbegin%7Bbmatrix%7D%20%5Cmathbf%7Br_%7B1%7D%7D%20%26%20%5Cmathbf%7Br_%7B2%7D%7D%20%26%20%5Cmathbf%7Br_%7B3%7D%7D%20%5Cend%7Bbmatrix%7D)

- Each  column is a 3D univector: ![eq:col_norm](https://latex.codecogs.com/gif.latex?%7C%7C%5Cmathbf%7Br_%7B1%7D%7D%7C%7C%20%3D%20%7C%7C%5Cmathbf%7Br_%7B2%7D%7D%7C%7C%20%3D%20%7C%7C%5Cmathbf%7Br_%7B3%7D%7D%7C%7C%20%3D%201)

- All columns are orthonomal to each other ![eq:col_prod](https://latex.codecogs.com/gif.latex?%5Cmathbf%7Br_%7B1%7D%7D%5ET%20%5Cmathbf%7Br_%7B2%7D%7D%20%3D%20%5Cmathbf%7Br_%7B1%7D%7D%5ET%20%5Cmathbf%7Br_%7B3%7D%7D%20%3D%20%5Cmathbf%7Br_%7B2%7D%7D%5ET%20%5Cmathbf%7Br_%7B3%7D%7D%20%3D%200)


#### Pros:
- Uniquely represents a rotation

#### Cons:
- 9 variables to represent 3 variables (redundant)


<!------------------------------------------------>

## 2. Euler Angles

### Rotate around <math>x</math> axis
![eq:rot_mat_x](https://latex.codecogs.com/gif.latex?R_x%20%3D%20%5Cbegin%7Bbmatrix%7D%201%20%26%200%20%26%200%20%5C%5C%200%20%26%20cos%28%5Ctheta_x%29%20%26%20-sin%28%5Ctheta_x%29%20%5C%5C%200%20%26%20sin%28%5Ctheta_x%29%20%26%20cos%28%5Ctheta_x%29%20%5Cend%7Bbmatrix%7D)


### Rotate around <math>y</math> axis
![eq:rot_mat_y](https://latex.codecogs.com/gif.latex?R_y%20%3D%20%5Cbegin%7Bbmatrix%7D%20cos%28%5Ctheta_y%29%20%26%200%20%26%20sin%28%5Ctheta_y%29%20%5C%5C%200%20%26%201%20%26%200%20%5C%5C%20-sin%28%5Ctheta_y%29%20%26%200%20%26%20cos%28%5Ctheta_y%29%20%5Cend%7Bbmatrix%7D)


### Rotate around <math>x</math> axis
![eq:rot_mat_y](https://latex.codecogs.com/gif.latex?R_z%20%3D%20%5Cbegin%7Bbmatrix%7D%20cos%28%5Ctheta_z%29%20%26%20-sin%28%5Ctheta_z%29%20%26%200%20%5C%5C%20sin%28%5Ctheta_z%29%20%26%20cos%28%5Ctheta_z%29%20%26%200%20%5C%5C%200%20%26%200%20%26%201%20%5Cend%7Bbmatrix%7D)

### Rotation using Proper Euler Angles (6 ways)

### Rotation using Trait-Bryan (6 ways)

### Gimbal Lock


<!------------------------------------------------>

## 3. Rodrigues Vector


<!------------------------------------------------>

## 4. Quaternion
