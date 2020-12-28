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

\begin{alignment}
\mathbf{R}(\phi, \theta, \psi) &= \begin{bmatrix}
cos(\psi)cos(\theta) & cos(\psi)sin(\theta)sin(\phi) - sin(\psi)cos(\phi) & cos(\psi)sin(\theta)cos(\phi) + sin(\psi)sin(\phi) \\
sin(\psi)cos(\theta) & sin(\psi)sin(\theta)sin(\phi) + cos(\psi)cos(\phi) & sin(\psi)sin(\theta)cos(\phi) - cos(\psi)sin(\phi) \\
-sin(\theta) & cos(\theta)sin(\phi) & cos(\theta)cos(\phi)
\end{bmatrix} \\
&= \begin{bmatrix}
r_{11} & r_{12} & r_{13} \\
r_{21} & r_{22} & r_{23} \\
r_{31} & r_{32} & r_{33}
\end{bmatrix}
\end{alignment}


<!------------------------------------------------>

## 1. Rotation Matrix

Rotation matrix is a 3x3 matrix which could represnt a unique rotation transformation:

![eq:rot_mat](https://latex.codecogs.com/gif.latex?%5Cmathbf%7BR%7D%20%3D%20%5Cbegin%7Bbmatrix%7D%20r_%7B11%7D%20%26%20r_%7B12%7D%20%26%20r_%7B13%7D%20%5C%5C%20r_%7B21%7D%20%26%20r_%7B22%7D%20%26%20r_%7B23%7D%20%5C%5C%20r_%7B31%7D%20%26%20r_%7B32%7D%20%26%20r_%7B33%7D%20%5Cend%7Bbmatrix%7D%20%3D%20%5Cbegin%7Bbmatrix%7D%20%5Cmathbf%7Br_%7B1%7D%7D%20%26%20%5Cmathbf%7Br_%7B2%7D%7D%20%26%20%5Cmathbf%7Br_%7B3%7D%7D%20%5Cend%7Bbmatrix%7D)

- Each  column is a 3D univector: ![eq:col_norm](https://latex.codecogs.com/gif.latex?%7C%7C%5Cmathbf%7Br_%7B1%7D%7D%7C%7C%20%3D%20%7C%7C%5Cmathbf%7Br_%7B2%7D%7D%7C%7C%20%3D%20%7C%7C%5Cmathbf%7Br_%7B3%7D%7D%7C%7C%20%3D%201)

- All columns are orthonomal to each other ![eq:col_prod](https://latex.codecogs.com/gif.latex?%5Cmathbf%7Br_%7B1%7D%7D%5ET%20%5Cmathbf%7Br_%7B2%7D%7D%20%3D%20%5Cmathbf%7Br_%7B1%7D%7D%5ET%20%5Cmathbf%7Br_%7B3%7D%7D%20%3D%20%5Cmathbf%7Br_%7B2%7D%7D%5ET%20%5Cmathbf%7Br_%7B3%7D%7D%20%3D%200)


### Pros and Cons of rotation matrix

#### Pros:
- Uniquely represents a rotation

#### Cons:
- 9 variables to represent 3 variables (redundant)



<!------------------------------------------------>

## 2. Euler Angles

Euler angles are a set of three angles representing rotations around three (x, y, z) axises.


### Right Hand Rule

- x-axis forward, from the index finger
- y-axis left, from the middle finger
- z-axis up, from the thumb finger
- **Roll** ![roll](https://latex.codecogs.com/gif.latex?%5Cphi) about x-axis
- **Pitch** ![pitch](https://latex.codecogs.com/gif.latex?%5Ctheta) about y-axis
- **Yaw** ![yaw](https://latex.codecogs.com/gif.latex?%5Cpsi) about z-axis


### Elementary rotations

#### Rotate around <math>x</math> axis (![eq:rx](https://latex.codecogs.com/gif.latex?%5Ctheta_x%20%3D%20%5Cphi))

![eq:rot_mat_x](https://latex.codecogs.com/gif.latex?R_x%20%3D%20%5Cbegin%7Bbmatrix%7D%201%20%26%200%20%26%200%20%5C%5C%200%20%26%20cos%28%5Ctheta_x%29%20%26%20-sin%28%5Ctheta_x%29%20%5C%5C%200%20%26%20sin%28%5Ctheta_x%29%20%26%20cos%28%5Ctheta_x%29%20%5Cend%7Bbmatrix%7D)


#### Rotate around <math>y</math> axis (![eq:ry](https://latex.codecogs.com/gif.latex?%5Ctheta_y%20%3D%20%5Ctheta))

![eq:rot_mat_y](https://latex.codecogs.com/gif.latex?R_y%20%3D%20%5Cbegin%7Bbmatrix%7D%20cos%28%5Ctheta_y%29%20%26%200%20%26%20sin%28%5Ctheta_y%29%20%5C%5C%200%20%26%201%20%26%200%20%5C%5C%20-sin%28%5Ctheta_y%29%20%26%200%20%26%20cos%28%5Ctheta_y%29%20%5Cend%7Bbmatrix%7D)


#### Rotate around <math>x</math> axis (![eq:rz](https://latex.codecogs.com/gif.latex?%5Ctheta_z%20%3D%20%5Cpsi))

![eq:rot_mat_y](https://latex.codecogs.com/gif.latex?R_z%20%3D%20%5Cbegin%7Bbmatrix%7D%20cos%28%5Ctheta_z%29%20%26%20-sin%28%5Ctheta_z%29%20%26%200%20%5C%5C%20sin%28%5Ctheta_z%29%20%26%20cos%28%5Ctheta_z%29%20%26%200%20%5C%5C%200%20%26%200%20%26%201%20%5Cend%7Bbmatrix%7D)


### Rotation matrix to elementary Euler angles

A rotation matrix can be formed from a maximum of 3 sequential rotations about the primary axes:

![eq:mat_to_euler](https://latex.codecogs.com/gif.latex?%5Cmathbf%7BR%7D%28%5Cphi%2C%20%5Ctheta%2C%20%5Cpsi%29).

- These rotations can be in any sequence, but not the same axis in succession. Since rotating along the same axis twice equals to rotating the axis once with a large angle. ![eq:two_euler](https://latex.codecogs.com/gif.latex?%5Cmathbf%7BR%7D_x%28%5Cphi%29%5Cmathbf%7BR%7D_x%28%5Cphi%29%20%3D%20%5Cmathbf%7BR%7D_x%282%5Cphi%29)

- In total there are 3x2x2 = **12 combinations**.


#### Euler Angles

Rotate along on axis twice (1st and 3rd), 3x2x1 = 6.
- XYX
- XZX
- YXY
- YZY
- ZXZ
- ZYZ


#### Cardan (or Tait–Bryan) Angles

Rotate along each primary axis once, 3x2x1 = 6.
- XYZ
- XZY
- YXZ
- YZX
- ZXY
- ZYX


#### Order of rotations is important
- e.g. ![eq:euler_order](https://latex.codecogs.com/gif.latex?%5Cmathbf%7BR%7D_x%5Cmathbf%7BR%7D_y%5Cmathbf%7BR%7D_z%5Cneq%5Cmathbf%7BR%7D_z%5Cmathbf%7BR%7D_y%5Cmathbf%7BR%7D_x)
- Matrices are not commutative.


#### Roll, Pitch, and Yaw from Rotation

If rotating around z-axis, then y-axis, then x-axis, you can solve the roll pitch and yaw angles from Rotation matrix,

![eq:mat_to_roll_pitch_yaw_2](https://latex.codecogs.com/gif.latex?%5Cphi%20%3D%20atan2%28r_%7B32%7D%2C%20r_%7B33%7D%29%5C%5C%20%5Cpsi%20%3D%20atan2%28r_%7B21%7D%2C%20r_%7B11%7D%29%5C%5C%20%5Ctheta%20%3D%20%5Cbegin%7Bcases%7D%20atan2%28-r_%7B31%7D%2C%20%5Cfrac%7Br_%7B21%7D%7D%7Bsin%28%5Cpsi%29%7D%29%2C%20%26%20%5Ctext%7Bif%7D%5C%20cos%28%5Cpsi%29%3D0%20%5C%5C%20atan2%28-r_%7B31%7D%2C%20%5Cfrac%7Br_%7B11%7D%7D%7Bcos%28%5Cpsi%29%7D%29%2C%20%26%20%5Ctext%7Botherwise%7D%20%5Cend%7Bcases%7D)


### Gimbal Lock

When the pich angle is pi/2, then we can not distinguish the roll and yaw angles:

![eq:gimbal_lock](https://latex.codecogs.com/gif.latex?%5Cbegin%7Balignment%7D%20%5Cmathbf%7BR%7D%28%5Cphi%2C%20%5Ctheta%2C%20%5Cpsi%29%20%26%3D%20%5Cbegin%7Bbmatrix%7D%200%20%26%200%20%26%201%20%5C%5C%20cos%28%5Cpsi%29sin%28%5Cphi%29%20&plus;%20sin%28%5Cpsi%29cos%28%5Cphi%29%20%26%20cos%28%5Cpsi%29cos%28%5Cphi%29%20-%20sin%28%5Cpsi%29sin%28%5Cphi%29%20%26%200%20%5C%5C%20-cos%28%5Cpsi%29cos%28%5Cphi%29%20&plus;%20sin%28%5Cpsi%29sin%28%5Cphi%29%20%26%20sin%28%5Cpsi%29cos%28%5Cphi%29%20&plus;%20cos%28%5Cpsi%29sin%28%5Cphi%29%20%26%200%20%5Cend%7Bbmatrix%7D%20%5C%5C%20%26%3D%20%5Cbegin%7Bbmatrix%7D%200%20%26%200%20%26%201%20%5C%5C%20sin%28%5Cpsi&plus;%5Cphi%29%20%26%20cos%28%5Cpsi&plus;%5Cphi%29%20%26%200%20%5C%5C%20-cos%28%5Cpsi&plus;%5Cphi%29%20%26%20sin%28%5Cpsi&plus;%5Cphi%29%20%26%200%20%5Cend%7Bbmatrix%7D%20%5Cend%7Balignment%7D)


### Pros and Cons of Euler angles

#### Pros:
- Easy to understand
- Less variables

#### Cons:
- Gimbal lock



<!------------------------------------------------>

## 3. Rodrigues Vector

Instead of rotate a vector  by multiplying a [3x3] rotation matrix, we can use the Rodrigues formula to rotate the vector.

### Rodrigues transform

Let the original vector be **u**, we now rotate it around a direction vector **n** by angle ![alpha](https://latex.codecogs.com/gif.latex?%5Calpha).  The obtained vector **v** can be denoted as:

![eq:rodrigue](https://latex.codecogs.com/gif.latex?cos%28%5Calpha%29%5Cmathbf%7Bu%7D%20&plus;%20%281%20-%20cos%28%5Calpha%29%29%28%5Cmathbf%7Bn%7D%5Ccdot%5Cmathbf%7Bu%7D%29%5Cmathbf%7Bn%7D%20&plus;%20sin%28%5Calpha%29%28%5Cmathbf%7Bn%7D%5Ctimes%5Cmathbf%7Bu%7D%29)

Dirivation of above equation can be found online.  Here is a [Youtube's derivation](https://www.youtube.com/watch?v=Fh3nMi87cB8) which I think is clear and vivid.


### Rodrigues vector [1x3]

We can then use a [1x3] vector to represent the Rodrigues transform:

![eq:rod_vect](https://latex.codecogs.com/gif.latex?%5Cmathbf%7BRod%7D%20%3D%20%28a_1%2C%20a_2%2C%20a_3%29%2C%20%7C%5Cmathbf%7BRod%7D%7C%20%3D%20%5Calpha%2C%20%5Cfrac%7B%5Cmathbf%7BRod%7D%7D%7B%7C%5Cmathbf%7BRod%7D%7C%7D%20%3D%20%5Cmathbf%7Bn%7D)


### Rodrigues Vector and Rotation Matrix

Since,

![eq_cross_prod](https://latex.codecogs.com/gif.latex?%5Cmathbf%7Bn%7D%20%5Ctimes%20%5Cmathbf%7Bu%7D%20%3D%20%5Cbegin%7Bbmatrix%7D%200%20%26%20-n_x%20%26%20n_y%20%5C%5C%20n_z%20%26%200%20%26%20-n_x%20%5C%5C%20-n_y%20%26%20n_x%20%26%200%20%5Cend%7Bbmatrix%7D%5Cbegin%7Bbmatrix%7D%20u_x%20%5C%5C%20u_y%20%5C%5C%20u_z%20%5Cend%7Bbmatrix%7D%20%3D%20%5Cmathbf%7BN%7D%5Cbegin%7Bbmatrix%7D%20u_x%20%5C%5C%20u_y%20%5C%5C%20u_z%20%5Cend%7Bbmatrix%7D)

We can obtain:

![eq:rod_mat](https://latex.codecogs.com/gif.latex?%5Cmathbf%7Bv%7D%20%3D%20%5Cmathbf%7Bu%7D%20&plus;%20sin%28%5Calpha%29%5Cmathbf%7BN%7D%5Cmathbf%7Bu%7D%20&plus;%20%281-cos%28%5Calpha%29%29%5Cmathbf%7BN%7D%5E2%5Cmathbf%7Bu%7D%20%3D%20%5Cmathbf%7BR%7D%5Cmathbf%7Bu%7D)


![eq:rod_mat_2](https://latex.codecogs.com/gif.latex?%5Cmathbf%7BR%7D%20%3D%20%5Cmathbf%7BI%7D%20&plus;%20sin%28%5Calpha%29%5Cmathbf%7BN%7D%20&plus;%20%281-cos%28%5Calpha%29%29%5Cmathbf%7BN%7D%5E2)


### Pros and Cons of Rodrigues vector

#### Pros:
- No Gimbal lock
- Less variables than rotation matrix

#### Cons:
- Rodrigues parameters have a singularity at ![eq:singularity](https://latex.codecogs.com/gif.latex?%5Calpha%20%3D%20180%5E%5Ccirc).



<!------------------------------------------------>

## 4. Quaternion

We can use a quaternion of 4 variables to represent rotation: (w, x, y, z).

![eq:quaternion](https://latex.codecogs.com/gif.latex?q%20%3D%20%28w%2C%20x%20i%2C%20y%20j%2C%20z%20k%29)


### Quaternion and Rodrigues Vector

Let the original vector be **u**, we now rotate it around a direction vector **n** by angle ![alpha](https://latex.codecogs.com/gif.latex?%5Calpha), and we obtain the new vector **v**. Then,

![eq:quat_rod](https://latex.codecogs.com/gif.latex?%5Cbegin%7Balignment%7D%20w%20%26%3D%20cos%28%5Cfrac%7B%5Calpha%7D%7B2%7D%29%5C%5C%20x%20%26%3D%20u_x%20%5Ccdot%20sin%28%5Cfrac%7B%5Calpha%7D%7B2%7D%29%5C%5C%20y%20%26%3D%20u_y%20%5Ccdot%20sin%28%5Cfrac%7B%5Calpha%7D%7B2%7D%29%5C%5C%20z%20%26%3D%20u_z%20%5Ccdot%20sin%28%5Cfrac%7B%5Calpha%7D%7B2%7D%29%5C%5C%20%5Cend%7Balignment%7D)


### Pros and Cons of Rodrigues vector

#### Pros:
- No Gimbal lock
- Less variables than rotation matrix

#### Cons:
- (w, i, j, k) and (-w, -i. -j. -k) describe the same rotation.
