[[Monomodal registration]]

## Introduction

Registration is the determination of a geometrical transformation that aligns points in one view of an object with corresponding points with another view. The word "view" is used generically to include three and two dimensional images or physical arrangement of an object in space.

Some common used "terminology":
- "Fusion" - Creation of something new as a mixture of the existing
- "Warping" - Bending or twisting out of shape
- "Matching" - Finding resemblance between the items


The goal of registration is with taking the two views as an input then get an output that is a geometrical transformation, which is a mathematical mapping from points in one view to points in the second.

Correspondence determination is one of the first steps in image registration. This involves finding the equivalent points or areas in different images that correspond the the same physical structure in the object. 

Image registration is often a subsystem, part of a larger system. 

If the registration has been successful the two images can be combined or fused together to create an image that can be more informative than the single images. Fusing images can be done in multiple ways:

- Summing the intensity values, this can highlight the areas of change or differences. 
- The outlines from one image can be superimposed onto the other, allowing for a clear comparison between the images. 
- Encoding the hue ang brightness, this allows for distinct differentiation between the images. 


### Registration - and ill-posed problem
Image registration is an ill-posed problem since it has many degrees of freedom compared to the available data. In other words, given a set of pixel intensities, find a vector (deformation) for each position - the number of unknowns is greater than the number of constraints. Rotational symmetry of objects affects uniqueness of the solution also. The solution is to restrict the set of possible transformation $\phi$, optimize.  

### The basic idea
The basic idea of image registration is:
Take the reference and evaluate the cost function with the observed image after the observed image has been transformed with initial transformation parameters. Check if the solution has converged, if not, choose a new set of parameters and repeat. The cost function can for example check how the images overlap. 

#### How to do it?
1. Define a set of allowed transformations $\phi$ 
2. Define a useful measure of similarity
3. Choose a practical optimization procedure

## Classification of registration methods
There are many image registration methods and they can be classified in many ways. Fitzpatrick et.al ()

[[Intensity based registration]]
- [[Similarity measures]]
- Optimization 

[[Feature-based registration]]
Feature detection, description, matching 
Transformation estimation


