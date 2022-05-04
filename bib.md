# Understanding and Explaining Deep Neural Networks for Vision 👀
Keen You (keen.you@yale.edu)
### Overview
***
Some background materials for explainable and interpretable AI systems with a focus on computer vision tasks. Meant to serve as inspirations for the final project and a starting point for further investigations.

### Papers
***
- **Explainable Artificial Intelligence: Understanding, Visualizing and Interpreting Deep Learning Model** (2017) [[paper]](https://arxiv.org/pdf/1708.08296.pdf)  
The paper introduces two popular methods that explain deep learning model predictions, where the output is a heatmap visualizing the importance of each pixel for a prediction. Specifically, ***sensitivity analysis  (SA)*** quantifies the importance of each input variable using partial derivatives, ie. which pixels need to be changed to make the iamge look more like the predicted class. On the other hand, ***layer-wise relecance propagation (LRP)*** redistributes the prediction score backwards and assigns a relevance score to each input variable. These methods can be evaluated using perturbation analysis, where we observe prediction score decline by perturbing input variables that are claimed to be important. (software: LRP toolbox)
- **Explanations for Attributing Deep Neural Network Predictions** (2019) [[paper]](https://doi.org/10.1007/978-3-030-28954-6_8) #8  
The paper introduces the Meta-Predictors as Explanation framework, which can be instantiated using Meaningful Perturbations. The goal is to summarize the effect of deleting different image regions on prediction. This can be framed as a deletion game, where we want to find the smallest deletion mask (blur, constant, and noise) such that the prediction score on the perturbed image drops significantly and can be modeled as a learning problem. The deletion game removes enough evidence to prevent the network from recognition whereas the symmetric preservation game finds a minimal subset of sufficient evidence. 
- **Interpreting Deep Visual Representations via Network Dissection** (2018) [[paper]](https://arxiv.org/pdf/1711.05611.pdf) [[website]](http://netdissect.csail.mit.edu)  
This paper proposes network dissection as a means to use disentangled represention to understand deep neural networks, where interpretability is defined to be the degree of alignment with human-interpretable concepts. The measure is quantified using three steps: 1) identify human-labeled visual concepts; 2) gather response of hidden variables to known concepts; 3) quantify alignment of hidden variable-concept pair. Dataset used is Broden, which consists of multiple datasets with labels of colors, materials, textures, parts, objects, and scenes.
- **Generating Post-Hoc Rationales of Deep Visual Classification Decisions** (2018)  [[paper]](https://link.springer.com/chapter/10.1007/978-3-319-98131-4_6)  
This paper introduces Generating Visual Explanations (GVE) as a framework to explain predictions of vision systems. GVE is based on [[LRCN]](https://arxiv.org/pdf/1411.4389.pdf), but with two modifications to increase image relevance of generated explanations. First, category predicitons are used addtionally to generate output sequence. Second, category-specific image features are incorporated into the system. Dataset used is UCSD Birds with detailed description of pictures as gold labels.
- **Deep Inside Convolutional Networks: Visualising Image Classification Models and Saliency Maps** (2014) [[paper]](https://arxiv.org/pdf/1312.6034.pdf)  
This paper introduces two methods for visualizing deep convolutional neural networks. The first method generates an image which maximizes class prediction score. The second method computes a image-specific class saliency map, which queries the evidence in the image for a specific class prediction.

### Other Resources
***  
- cs231n lecture 12 Visualizing and Understanding [[video]](https://www.youtube.com/watch?v=6wcs6szJWMY) [[slides]](http://cs231n.stanford.edu/slides/2017/cs231n_2017_lecture12.pdf)
Introduces various visualization techniques including visualize raw filters, nearest neighbors of last layer, dimensionality reduction of last layer, visualizing activations, maximally activating patches, occlusion experiments, saliency maps, and intermediate features via backprop.
- Deep Visualization Toolbox [[video]](https://www.youtube.com/watch?v=AgkfIQ4IGaM) [[website]](https://yosinski.com/deepvis)
- How convolutional neural networks see the world [[blogpost]](https://blog.keras.io/how-convolutional-neural-networks-see-the-world.html)
