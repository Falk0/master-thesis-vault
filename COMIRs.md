The method is supervised but thanks to using a sophisticated scheme for creating training data, as little as one image can be sufficient to the COMIRs, this is of course depending on the nature of the image and may vary. 

While [[Image-to-image translation]] aims to predict cross-modality, meaning that it predicts one modality given the other modality. The COMIR method learns representations called CoMIRs, thats rely on the mutual information by maximizing the Mutual Information Noise-Contrastive Estimation (InfoNCE). [[InfoNCE]] can for some assumptions act as a lower bound to mutual information (What assumptions?).  

In the COMIR method, contrastive learning is applied to aligned pairs of images during training to create dense representations. To the learnt representations can then be processed with monomodal registration algorithms since the method doesn't require any additional information about the modalities at hand.   

This approach prioritises extracting and aligning common features between modalities, rather than translating one image's appearance to resemble another's.

[[Multimodal images]]

[[Cyclic Group]]

[[Image registration]]

[[Contrastive loss]]