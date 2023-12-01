A quantitative metric used to evaluate how closely two images resemble each other, when taking into account factors such as intensity, color, texture or geometric alignment. 

### Similar and dissimilar images
Similar images are often produced with the same camera, with the same modality and the same object (a patient for an example). Less similar images comes from different imaging conditions (light and contrast), from different modalities (CT,MRI,PET, Ultrasound), different time of acquisition and of different dimensionality (2D to 3D)

### Image similarity - Intensity based methods
There are multiple methods to measure the similarity or dissimilarity between the transformed source image $\phi(B)$ and the target $A$:
- **Sum of squared differences** (dissimilarity)
- **Pearson Correlation Coefficient** (similarity)
- **Mutual information** (similarity)

These methods are based on **pointwise** comparison between pixels in $\phi(B)$ and $A$. Comparing pixel values in $\phi(B)$ and $A$, sweep and average/sum/aggregate over the whole image $\phi(B)$ where it overlaps with A. 


#### Sum of squared differences (SSD)
For two image $A$ and $B$ and for all positions $(x,y)$ in their region of overlap $O(A,B)$:

$$ \text{SSD}(A,B) = \sum_{(x,y) \in O(A,B)} \big( A(x,y) - B(x,y) \big)^2$$
The pros for this method is that it is very simple, intuitive and fast. The cons are that is that the signals must have the same brightness and contrast and it doesn't work on different modalities. It is not appropriate to use this method when there are linear intensity changes in the images. This can be mitigated by normalizing the images before using SSD. 