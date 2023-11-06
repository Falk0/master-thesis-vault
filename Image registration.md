**Image registration** is the process of finding correspondence between images of the same or similar scene. **Multimodal image registration** is the specific case when the images are captured with different imaging systems. In other words: finding transformations matching unaligned images. 

There are two main types:
- **Featured-based**
	- Extract a set of feature points between which a correspondence is found
- __Intensity based__ 
	- Uses the voxel values directly, evaluate candidate mappings based on [[Similarity measures]] (affinity). 

Image selected as either floating or reference image. Treating them separately can introduce a source of asymmetry if for example interpolation is used.

[[Fuzzy sets]] 

### Intensity-based registration
In general a non-convex optimization problem with a large number of local optima. To overcome this, a resolution-pyramid-scheme is often used. Smooth low resolution images are then first registered and are then followed with images with increasing resolution and decreased degree of smoothing, a coarse-to-fine-approach. 


In deformable image registration the images are assumed to be misaligned with local deformation(?). In these cases must the registration be performed locally. 

[[COMIRs]] are a type of image representation that is learned through [[Contrastive loss]] (**CL**)  


