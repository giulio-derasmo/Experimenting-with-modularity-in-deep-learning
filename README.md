# Experimenting with modularity in deep learning

The project is carried out for the course Neural Networks for Data Science at Sapienza, with the aim to have an hands-on with the recent field of Modular Networks.
Modular Networks aim to provide an alternativy to tecnique like Distillation in order to reduce the training and inference time or the overall computational budget given by the deep architecture going more deeper nowadays. 

## The model and training

The type of modular networks I implement is Early Exit over a VGG13 model in Tensorflow Keras for image classification given the [flower](https://www.tensorflow.org/datasets/catalog/tf_flowers) dataset. More specifically I add fixed early exits in the previous architecture and train the new model with a Joint Cross Entropy loss using all the early exit prediction and the final one. Inference is done by a thresholding operation on the entropy of the early exit layer  e  that ensure if exit early or continue. The Early-Exit layer is a small classifier of two sequential layer: convolution and a fully connected one. The early exit branch are implemented after every convolutional block in the model, for a total of 5, in order to explore more this modular architecture.

## References 

[1][Why should we add early exits
to neural networks?](https://arxiv.org/pdf/2004.12814.pdf)

[2][DeeBERT: Dynamic Early Exiting for Accelerating BERT Inference](https://arxiv.org/pdf/2004.12993.pdf)

[3][Going deeper with convolutions](https://arxiv.org/pdf/1409.4842.pdf )

#
<p align="center">
    <img src="https://user-images.githubusercontent.com/50860347/147412786-183da6b0-990f-4016-9f2e-0719d8066f5b.png" style="width: 100%"/>
<p>
