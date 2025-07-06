**Siamese network for image classification:**

Siamese Neural Network (SNN) is an architecture based on CNN and designed to recognize images. How?
The model is actually built from 2 identical CNN networks, each of which receives an image. After processing the image in each network, the networks are connected and merged into a network that measures the 'distances' between the two images, that is, how much the images are the same/different. 

**There is a special loss function for SNN - contrastive loss, and it is actually the one that measures the distances.**
<img width="501" alt="‏‏לכידה" src="https://github.com/user-attachments/assets/a34f88cc-899f-4277-aff0-6382418200cb" />

For example, if we enter two images of a dog - we expect to see a small distance. If we enter one image of a dog and one of a cat - we expect to see a larger distance.
this are pairs of pictures with labels:
![image](https://github.com/user-attachments/assets/d40e1cd9-e8fb-48c9-8ac2-f66da851e45f)

In addition, already during training we expect to see the learning process of the network expressed in the fact that the distances between identical images are small (= called: positive distance) and the distances between different images increase (= called: negative distance).
![image](https://github.com/user-attachments/assets/ac04330e-8aa5-452e-836e-5b58b2679ca4)

During training, the pairs are inserted each time and the model learns the distances. Then, pairs from the test are run on it and the prediction it gives is seen - whether it marked a pair of different images as far enough apart, and a pair of identical images as close enough.
The uniqueness of the Siamese network is that it does not test a single image. It is always compared to something else. On the other hand, since it is two CNNs running in parallel, it is a very powerful tool that gives reliable and efficient results.
we use a pre-trained model and performed transfer-learning to adjust it to our needs(we used DeneNet121).

**SNN advantage over CNN**

We ran CNN against the SNN network to test the effectiveness of the siamese network and came to the conclusion: A siamese network is particularly effective for small medical data, because it is classified by creating random pairs and calculating the distances between them. The random pairs created in each epoch significantly increase our data, and thus the network can learn better and produce good results even on complicated data.
Compared to CNN, which classifies data differently, not by pairs, and therefore gives less good results on small data sets.

**The result**


