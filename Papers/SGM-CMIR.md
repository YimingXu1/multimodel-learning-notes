# Cross-modal Scene Graph Matching for Relationship-aware Image-Text Retrieval

## Overview

Natural scenes image mainly involves two kinds of visual concepts: object and their relations, which are equally essential to image-text retrieval. Intuitively, compared to CNN-based methods, Graph-based image feature contains more important visual information and considers the relationship between objects.

This paper use represent image and text with respectively visual scene graph (VSG) and textual scene graph (TSG), then CMIR tasks is naturally formulated as cross-modal scene graph matching.

This method enables us to obtain both object-level and relationship-level cross-modal features, which favorably enables us to evaluate the similarity of image and text in the two levels in a more plausible way. 

## Motivation and Contributions

![alt img](https://github.com/YimingXu1/multimodel-learning-notes/blob/main/Papers/ref/SGM-CMIR0.jpg)

As shown in the top of the figure, early approaches use global representations to express the whole image and sentence, which ignore the local details. These methods work well on simple cross-modal retrieval scenario, but not performance good at more realistic cases that involve complex natural scenes. 

Recent studies pay attention to local detailed matching by detecting objects in both images and text, but ignore the relationships. 

In this paper, authors organize the objects and the relationships into scene graphs for both modalities, converting the conventional image-text retrieval problem to the matching of two scene graphs.

**Contributions**

- Extract objects and relationships from the image and text to form the VSG and TSG, and design a so-called Scene Graph Matching (SGM) model.
- The VSG encoder is a Multi-modal Graph Convolution Network (MGCN), which enhances the representations of each node on the VSG by aggregating useful information from other nodes and updates the object and relationship features in different manners.
- The TSG encoder contains two different bi-GRUs aiming to encode the object and relationship features, respectively.
- Both object-level and relationship-level features are learned in each graph, and the two feature graphs corresponding to two modalities can be finally matched at two levels in a more plausible way.

## Methodology

### Visual Scene Graph Generation

![alt img](https://github.com/YimingXu1/multimodel-learning-notes/blob/main/Papers/ref/SGM-CMIR1.jpg)

Given a raw image, represent a visual scene graph as $G = \{V, E\}$, $V$ is the node-set, and $E$ is the edge-set.  As shown in figure, the pink rectangles denote object nodes, each of which corresponds to a region of the image. The ellipses in light blue are relationship nodes, each of which connects two object nodes by directed edges.

### Visual Scene Graph Encoder