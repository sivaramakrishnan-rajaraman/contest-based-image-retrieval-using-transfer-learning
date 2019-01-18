# contest-based-image-retrieval-using-transfer-learning

Please feel free to use the jupyter notebook made available here. I have used a pre-trained VGG-19 model to find similar images in a given set of data by dissecting the trained weights and using them for feature extraction. We call it Transfer Learning (TL) since the model has already been trained on ImageNet with more than 14 million annotated images belonging to 21K categories. Despite the trained model’s inability to detect foreign high-level features from your dataset of interest it may not have seen before, the low-level features including edges, colors and textures are transferable because of their great abundance and variety in the ImageNet data. With this in mind, I used a pre-trained VGG-19 and truncated the layers for extracting features from the underlying data. The similarities between the images can be compared directly with these feature vectors by performing inner-products such as Euclidean distance or cosine similarity toward clustering the images.


Kindly cite the following publication if you find this notebook useful: 

#### Sivaramakrishnan Rajaraman, Sameer Antani. 2018. Visualizing salient network activations in convolutional neural networks for medical image modality classification. In: Proceedings of the 2018 International Conference on Recent Trends in Image Processing & Pattern Recognition (RTIP2R), December 21-22, Solapur, Maharashtra state, INDIA 


# prerequisites:

Keras >= 2.2.0

Tensorflow >= 1.9.0

Jupyter (I have Anaconda3 5.1.0)


# Steps involved:

•	Database preparation.

•	A trained model of preference and truncating the layers. 

•	Feature extraction from the underlying data. 

•	Flattening the filters and appending them to make a single vector.

•	Computing similarities between the image feature vectors using Euclidean distance or cosine similarity.

•	Selecting the top-k similarity scores for each image.

•	Running the t-SNE algorithm (a dimensionality reduction algorithm, please refer to Wikipedia) with the extracted feature vectors and projecting them in the 2-dimensional space to show how the similar images are projected. 

I have used six classes and six images per class. VGG-19 was performing a good job however it wasn’t commendable in extracting similar images across the CT and MRI categories. You can try with your data and see how the model behaves. If everything is running smoothly, you can visualize the results in the folder “output_new.” 

Uou can opt to play with this notebook by:

•	Deploying the trained model of your preference.

•	Try changing the layers to extract features to arrive at the optimal results.

•	Try changing the KNN distance parameters, number of neighbors and observe its effects. 
