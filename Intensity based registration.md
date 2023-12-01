### Geometric transformations
Linear transformations can be described as matrix multiplications, translation most be included in the case of homogeneous coordinates. 

$$ \begin{bmatrix}
y_{1}\\ y_{2}\\ 1
\end{bmatrix} = \begin{bmatrix}
h_{11} & h_{12} & h_{13}  \\ h_{21}& h_{22}& h_{23}  \\ h_{31} & h_{32} & h_{33}
\end{bmatrix} \begin{bmatrix}
x_{1} \\ x_2 \\ 1
\end{bmatrix}$$

#### Projective (2D):
This is a 2D transformation method that can map one image to another, this typically involves changes in the viewpoint or geometry. It maps lines to lines but does not preserve parallelism. It can represent more complex changes in perspective than simpler transformations such as rotation and scaling. The method is a Homography which means that it is a specific type of projective transformation that relates two images of the same planar surface in space. It is useful in tasks like image stitching or when compensating for changes in viewpoint. 

$$ \begin{bmatrix}
y_{1}\\ y_{2}\\ 1
\end{bmatrix} = \begin{bmatrix}
h_{11} & h_{12} & h_{13}  \\ h_{21}& h_{22}& h_{23}  \\ h_{31} & h_{32} & h_{33}
\end{bmatrix} \begin{bmatrix}
x_{1} \\ x_2 \\ 1
\end{bmatrix}$$

$$y_{1} = \frac{h_{11}x_{1}+ h_{12}x_{2} + h_{13}}{h_{31}x_{1}+ h_{32}x_{2} + h_{33}} \quad y_{2} = \frac{h_{21}x_{1}+ h_{22}x_{2} + h_{23}}{h_{31}x_{1}+ h_{32}x_{2} + h_{33}}$$

A homography in 2D space has 8 Degrees of freedom (DoF) which means that it can be defined by 8 independent parameters. These parameters determine how each point in the image relates to the corresponding point in the other image. To compute the Homography we need at least 4 pairs of corresponding points from the images. Each point pair provides two equations, one for the x-axis and one for the y-axis, a total of 8 equations from 4 points. These are needed to solve for the 8 parameters of the Homography matrix. This will allow the transformation to shift in position, scale, rotate and perspective distortion. 

The projective transformation preserves the collinearity and concurrency which means that it doesn't disturb the straight-line relationship among points (point on a straight line, remains on the line). This preserves the structural integrity of the scene in the image, this is useful when having building in the image. The edges of the building in the image will remain straight after the transformation, even though their position and angle may change. 

#### Affine transformations
This type of transformation is a linear mapping method that preserves: points, straight lines and planes. It transforms images by translating, scaling, rotating, or shearing them. Like in the case of projective transformation, it preserves collinearity but unlike the projective it also preserves parallell lines. It can be viewed a combination of multiple basic transformations. 

An affine transformation in 2D space usually has 6 degrees of freedom. 2 for translation, 1 for shearing, 1 for rotations, 1 for scale along x-axis and 1 for scaling the y-axis. Three points are required to solve the total of 6 equations for the 6 parameters, 6 degrees of freedom. 

$$ y = Ax +t \quad \begin{bmatrix}
y_{1} \\ y_{2}  \\ 1
\end{bmatrix} = \begin{bmatrix}
a_{11} & a_{12} & t_{1} \\ a_{21} & a_{22} & t_{2} \\ 0 & 0 & 1 
\end{bmatrix} \begin{bmatrix}
x_1 \\ x_2 \\ 1
\end{bmatrix}$$
$$ \textbf{y} = \begin{bmatrix}
\textbf{A} & \textbf{t} \\ \textbf{0}^{T} & 1
\end{bmatrix}\textbf{x}$$

#### Similarity transformations 
A similarity transformation is a type of affine transformation that preserves the shape of an object but allow for scaling, rotation and translation. But unlike the affine transformations it maintains the proportions and angles of the original scene/figure. It characteristics include that it can be seen as an combination of transformations. These combinations include: uniform scaling, meaning that is rescales with the same factor in all directions, rotation and translation. This transformation also preserves collinearity and parallelism. It has a degree of freedom of 4 usually, two for translation, 1 for rotation and 1 for scaling.  

$$ \begin{bmatrix}
y_{1} \\ y_{2}  \\ 1
\end{bmatrix} = \begin{bmatrix}
s\cos \theta & -s \sin \theta & t_{1} \\ s\sin \theta & s \cos \theta & t_{2} \\ 0 & 0 & 1 
\end{bmatrix} \begin{bmatrix}
x_1 \\ x_2 \\ 1
\end{bmatrix}$$

$$\textbf{R}\textbf{R}^{T}= \textbf{I} \quad \text{ and } \det(\textbf{R}) = 1$$
#### Rigid transformations
This form of transformations is the most restrictive form of affine transformations since it only allows rotation and translation, with no scaling or shearing. Here the distance between two points in the original image is preserved. The lengths are rigid. The angles are also preserved. It has 3 degrees of freedom with the parameters: 2 for translation and 1 for rotation. 

#### Summary of Geometric transformations
If the problem has only one viewpoint (in other words: a camera in a fixed position) with rigid objects, then **similarity** is a good choice of transformation. If we have multiple viewpoints and rigid objects with relatively large distance to the scene, then **affine** transformations are a good choice. For the **projective** methods there should be a small distance to the object. 

### Parametric vs non-parametric transformations
In the case of parametric transformation we have a small set of parameters that is used while in the non-parametric case we have **large set of parameters**, every point has it's own parameters. Here we can visualise the transformation of each pixel with with a deformation field which indicates the displacement for each pixel. 


### A few words on interpolation
Linear transformations can transform points that are sampled inside the image grid to positions outside the grid. It is therefore required to use [[Interpolation]] to obtain the intensity at the transformed points location.

Interpolation can be a large source of error and bias in intensity-based [[Registration]]
