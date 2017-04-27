# tf-examples
A lot of TensorFlow code online is more complicated than necessary, at least for learning purposes. A few "advanced" features of TensorFlow are introduced along the way.

# Requirements
The code has been tested with Python 3.5 and TensorFlow 1.0.1.

# Notes

The results are reproducible on a CPU but not on GPUs.

## Datasets

* `datasets/iris/iris.txt` is a subset of the full [Iris flower dataset](https://archive.ics.uci.edu/ml/datasets/Iris) used to illustrate simple linear and logistic regression. It contains the sepal length, petal length, and species label for _Iris versicolor_ and _Iris virginica_.

## Simple linear regression with the Iris dataset

* `iris_linreg_np.py` implements linear regression in NumPy with batch gradient descent, i.e., each gradient is computed on the entire dataset.

```
After 10 epochs, loss = 0.119608573615551
After 20 epochs, loss = 0.11919780820608139
After 30 epochs, loss = 0.11916114389896393
After 40 epochs, loss = 0.11912454664707184
After 50 epochs, loss = 0.11908803135156631
After 60 epochs, loss = 0.11905158311128616
After 70 epochs, loss = 0.11901525408029556
After 80 epochs, loss = 0.11897895485162735
After 90 epochs, loss = 0.1189427524805069
After 100 epochs, loss = 0.11890660971403122
W = 0.771308
b = 0.102663
```

* `iris_linreg_tf.py` does the same with TensorFlow.

## Simple binary logistic regression with the Iris dataset

## Multiclass logistic regression with MNIST

## Convolutional neural network with MNIST

* `mnist_cnn.py` is a simplified version of the code from https://www.tensorflow.org/get_started/mnist/pros.

```
Variables
---------
conv1/W:0 (5, 5, 1, 32)
conv1/b:0 (32,)
conv2/W:0 (5, 5, 32, 64)
conv2/b:0 (64,)
fc/W:0 (3136, 1024)
fc/b:0 (1024,)
softmax/W:0 (1024, 10)
softmax/b:0 (10,)
=> Total number of parameters = 3274634

After 1 epochs, validation accuracy = 0.97079998254776
Test accuracy = 0.9733999967575073
```

* `mnist_cnn_model.py`, `mnist_cnn_train.py`, and `mnist_cnn_test` do the same but demonstrate a more canonical way to organize code for such projects. They also demonstrate how to use variable scopes, saving and restoring models, and using TensorBoard to monitor training progress.

## Variational autoencoder for MNIST

* `vae.py` is a simplified version of the code from https://jmetzen.github.io/2015-11-27/vae.html.
