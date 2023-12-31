# Hierarchical-Fern
## Self-supervised Camera Relocalization with Hierarchical Fern Encoding

**Date of release**: Our paper is currently under review, and our code will be released after our paper is accepted.

**Performance**: we conducted a comparative analysis of our proposed method for object relocalization with existing state-of-the-art techniques. The comparative results are presented in the following figure and table.
![](https://github.com/edwinlu-hdu/Hierarchical-Fern/blob/main/Qualitative%20Comparisons.png?raw=true)
![](https://github.com/edwinlu-hdu/Hierarchical-Fern/blob/main/Quantitative%20Comparisons.png?raw=true)

## Introduction
Visual relocalization plays a crucial role in unmanned systems, which automatically estimates the camera pose in a known scene with the input visual information.  However, existing visual relocalization methods encounter challenges in relocating images with significant viewpoint variations, and they often lack the ability to self-identify the precision of the relocated camera pose, leading to low accuracy and recall.  In this study, we propose a novel visual relocalization method that leverages a hierarchical image fern encoding and matching technique to accurately relocalize under large viewpoint differences. Furthermore, we introduce a self-supervised pose optimization module that self-identify the precision of the relocated camera poses and refines the false or inaccurate poses via a looped correction strategy. To identify the precision without ground truth, we translate the problem of precision identification into the classification of precision range and design a multi-SVM module to classify the precision range of a  relocated camera pose by the output values of the Iterative Closest Point (ICP). We evaluate our proposed method on two widely used datasets, 7-Scenes and 12-Scenes, and show that our method substantially reduces false positives in camera relocalization. In particular, our method achieves more than a 20\% improvement in recall with 1cm/1° accuracy compared to the state-of-the-art methods. 

# Requirements
Several 3rd party libraries are needed for compiling 3D reconstruction. The given version numbers are checked and working, but different versions might be fine as well. Some of the libraries are optional, and skipping them will reduce functionality.
- Ubuntu (e.g. 18.04 or 20.04)
- cmake (e.g. version 2.8.10.2 or 3.2.3) REQUIRED
- Eigen (e.g. version 3.3.5) REQUIRED
- OpenGL / GLUT (e.g. freeglut 2.8.0 or 3.0.0) REQUIRED for the visualisation
- CUDA (e.g. version 8.0) OPTIONAL but REQUIRED for all GPU accelerated code
- libpng (e.g. version 1.6) OPTIONAL, allows to read PNG input files
- OpenNI (e.g. version 2.2.0.33) OPTIONAL but REQUIRED to get live images from suitable hardware
