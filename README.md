**Siamese network for medical image classification**

This project demonstrates the use of a Siamese Neural Network (SNN) — a powerful deep learning architecture based on convolutional neural networks (CNNs) — for image classification tasks.

**What is a Siamese Neural Network?**

A Siamese Network consists of two identical CNNs that share weights and process two input images simultaneously. The outputs of the two CNNs are combined and passed through a distance function (e.g., contrastive loss) that measures the similarity or dissimilarity between the two images.

If the input images are similar (e.g., two images of the digit '3' or two dog photos), the network learns to produce small distances. If the images are different (e.g., a cat and a dog), the network produces larger distances.

![image](https://github.com/user-attachments/assets/ea583380-d52e-4d4b-8e93-eb5d9c40a2bf)
This approach makes the Siamese network especially effective in cases where the goal is to determine whether two inputs are from the same class, rather than classifying an image into a fixed set of categories.

**datasets**

we built snn models for 4 familiar datasets:

-MNIST

-cat-dogs

-brain-tumor

-chest-x-rest

 
**There is a special loss function for SNN - contrastive loss, and it is actually the one that measures the distances.**

![image](https://github.com/user-attachments/assets/f5ab5eec-8a14-4e1a-9da7-d966023a6b77)

For example, if we enter two images of a dog - we expect to see a small distance. If we enter one image of a dog and one of a cat - we expect to see a larger distance.
this are pairs of pictures with labels:

![image](https://github.com/user-attachments/assets/ea583380-d52e-4d4b-8e93-eb5d9c40a2bf)


In addition, already during training we expect to see the learning process of the network expressed in the fact that the distances between identical images are small (= called: positive distance) and the distances between different images increase (= called: negative distance).
![image](https://github.com/user-attachments/assets/ac04330e-8aa5-452e-836e-5b58b2679ca4)

During training, the pairs are inserted each time and the model learns the distances. Then, pairs from the test are run on it and the prediction it gives is seen - whether it marked a pair of different images as far enough apart, and a pair of identical images as close enough.
The uniqueness of the Siamese network is that it does not test a single image. It is always compared to something else. On the other hand, since it is two CNNs running in parallel, it is a very powerful tool that gives reliable and efficient results.
we use a pre-trained model and performed transfer-learning to adjust it to our needs(we used DeneNet121).

**SNN advantage over CNN**

We ran CNN against the SNN network to test the effectiveness of the siamese network and came to the conclusion: A siamese network is particularly effective for small medical data, because it is classified by creating random pairs and calculating the distances between them. The random pairs created in each epoch significantly increase our data, and thus the network can learn better and produce good results even on complicated data.
Compared to CNN, which classifies data differently, not by pairs, and therefore gives less good results on small data sets.
![image](https://github.com/user-attachments/assets/38c259c9-f8cb-47bc-809a-e465499446fe)




