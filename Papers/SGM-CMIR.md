# Cross-modal Scene Graph Matching for Relationship-aware Image-Text Retrieval

## Overview

Natural scenes image mainly involves two kinds of visual concepts: object and their relations, which are equally essential to image-text retrieval. Intuitively, compared to CNN-based methods, Graph-based image feature contains more important visual information and considers the relationship between objects.

This paper use represent image and text with respectively visual scene graph (VSG) and textual scene graph (TSG), then CMIR tasks is naturally formulated as cross-modal scene graph matching.

This method enables us to obtain both object-level and relationship-level cross-modal features, which favorably enables us to evaluate the similarity of image and text in the two levels in a more plausible way. 

## Motivation and Contributions

![alt img](https://github.com/YimingXu1/multimodel-learning-notes/blob/main/Papers/ref/SGM-CMIR0.jpg)

**Contributions**

- Extract objects and relationships from the image and text to form the VSG and TSG, and design a so-called Scene Graph Matching (SGM) model.
- The VSG encoder is a Multi-modal Graph Convolution Network (MGCN), which enhances the representations of each node on the VSG by aggregating useful information from other nodes and updates the object and relationship features in different manners.
- The TSG encoder contains two different bi-GRUs aiming to encode the object and relationship features, respectively.
- Both object-level and relationship-level features are learned in each graph, and the two feature graphs corresponding to two modalities can be finally matched at two levels in a more plausible way.



