**Siamese network for medical image classification**

This project demonstrates the use of a Siamese Neural Network (SNN) — a powerful deep learning architecture based on convolutional neural networks (CNNs) — for image classification tasks.

**What is a Siamese Neural Network?**

A Siamese Network consists of two identical CNNs that share weights and process two input images simultaneously. The outputs of the two CNNs are combined and passed through a distance function (e.g., contrastive loss) that measures the similarity or dissimilarity between the two images.

If the input images are similar (e.g., two images of the digit '3' or two dog photos), the network learns to produce small distances. If the images are different (e.g., a cat and a dog), the network produces larger distances.

<img src="https://github.com/user-attachments/assets/ea583380-d52e-4d4b-8e93-eb5d9c40a2bf" alt="example" width="300">

This approach makes the Siamese network especially effective in cases where the goal is to determine whether two inputs are from the same class, rather than classifying an image into a fixed set of categories.

**Datasets Used**
We applied our SNN model on four well-known datasets:

MNIST – Handwritten digits

Cats vs. Dogs

Brain Tumor MRI

Chest X-Ray Pneumonia Detection

**Training the Model**
 
For training, we used a contrastive loss function, which directly encourages the model to minimize the distance between similar image pairs and maximize the distance between dissimilar ones.

<img src="https://github.com/user-attachments/assets/f5ab5eec-8a14-4e1a-9da7-d966023a6b77" alt="example" width="300">

Throughout training, image pairs are dynamically generated, which increases the effective dataset size and helps reduce overfitting, especially in small medical datasets. We used transfer learning with a pre-trained DenseNet121 backbone to accelerate training and improve performance.

For example, if we enter two images of a dog - we expect to see a small distance. If we enter one image of a dog and one of a cat - we expect to see a larger distance.
this are pairs of pictures with labels:

In addition, already during training we expect to see the learning process of the network expressed in the fact that the distances between identical images are small (= called: positive distance) and the distances between different images increase (= called: negative distance).

<img src="https://github.com/user-attachments/assets/ac04330e-8aa5-452e-836e-5b58b2679ca4" alt="example" width="500">

During training, the pairs are inserted each time and the model learns the distances. Then, pairs from the test are run on it and the prediction it gives is seen - whether it marked a pair of different images as far enough apart, and a pair of identical images as close enough.
The uniqueness of the Siamese network is that it does not test a single image. It is always compared to something else. On the other hand, since it is two CNNs running in parallel, it is a very powerful tool that gives reliable and efficient results.
we use a pre-trained model and performed transfer-learning to adjust it to our needs(we used DeneNet121).
**You can view and download the trained model here:
(https://drive.google.com/drive/folders/1WDp9doYnxeKIel6-YnRzZ75z3gv1oos_?usp=sharing)**

**SNN advantage over CNN**

<img src="https://github.com/user-attachments/assets/c0286cb2-5b08-4a08-a04b-460448c51129" alt="example" width="300">

We ran CNN against the SNN network to test the effectiveness of the siamese network and came to the conclusion: A siamese network is particularly effective for small medical data, because it is classified by creating random pairs and calculating the distances between them. The random pairs created in each epoch significantly increase our data, and thus the network can learn better and produce good results even on complicated data.
Compared to CNN, which classifies data differently, not by pairs, and therefore gives less good results on small data sets.







