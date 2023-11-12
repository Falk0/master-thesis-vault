Linear transformations relates points in one space to another via an application of a linear function.  

A transformation is said to be rigid if only rotations and translations are permitted. 

Affine if shearing and reflections is also permitted. Affine transformations $T :\mathbb{R}^n \rightarrow \mathbb{R}^n$ can be expressed as matrix multiplication:
$$Tx = \begin{bmatrix} a_{11}& a_{12}& \cdots& a_{1n}& t_1 \\ 
 a_{11}& a_{12}& \cdots& a_{1n}& t_1 \\ 
 \vdots& \vdots& &  \vdots \\ a_{n1}& a_{n2}& \cdots& a_{nn}& t_N \\ 
 0& 0& \cdots 0& 0& 1 \end{bmatrix} \begin{bmatrix} x_1 \\ x_2 \\ \vdots \\ x_n \\ 1 \end{bmatrix}$$
Linear transformations can transform points that are sampled inside the image grid to positions outside the grid. It is therefore required to use [[Interpolation]] to obtain the intensity at the transformed points location.

Interpolation can be a large source of error and bias in intensity-based [[Registration]]


non-rigid transformations or non-linear (deformable) transformations includes transformations such as stretching and bending 