# Hadoop_with_Deep_NeuralNet
This project is set to use the hadoop streaming to implement tensorflow and Theano libraries in hadoop environment.

it will work like this. The mapper is going to partition the input data. For even partition the mapper will train a Convolutional
Neural Network and Odd partition it will implement and train Recurrent Neural Network. 
Hadoop send similar key element to same reducer.
Before reducder get call, we can employ combiner to create a list of CNN model and serialized  them and another combiner based on 
different key to ensemble and serialized RNN.

In reducer we can perform ensembling of two different deep neural nets using test dataset stored in a distributed cache. the trained models
need to be deserialized properly.

Initailly the models are designed to handle text and vision data. model designed for vision data can be suitably modified to handle any numeric data. 

the models are designed and developed to solve multiclass classification problem.

As output function I have used softmax function in order to get the normalized output. Softmax function helps me to get the generalized
distribution of output classes given the data. that is we are calculating P(Y|X).  Nature of true supervised discriminative model. Under
the assumption is the data are coming from identical distribution.

text data has both short and long term linear dependency and vision data has local neighorhood dependency. Both LSTM RNN and CNN can perfectly model this relationship. Therefore they perform really well in text analytics and computer vision problems like object detection

For cost function I have used cross entropy. Entropy is a way to measure the randomness of random variables. Uniform random variable has highest entropy as the masses are uniformly distributed across all point of uncertainity. This is the max uncertainity is achievable. The
 model tries to reduce the cross entropy given an input data. Because we want to reduce the unorderedness in the output layer given the input. We want one node in output layer group only one class reduces the entropy to zero.

The project look like a bit complicated but careful evaluation will make it seem easy and normal.
