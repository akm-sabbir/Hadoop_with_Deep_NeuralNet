# Hadoop_with_Deep_NeuralNet
This project is set to use the hadoop streaming to implement tensorflow and Theano libraries in hadoop environment.

it will work like this. The mapper is going to partition the input data. For even partition the mapper will train a Convolutional
Neural Network and Odd partition it will implement and train Recurrent Neural Network. 
Hadoop send similar key element to same reducer.
Before reducder get call, we can employ combiner to create a list of CNN model and serialized  them and another combiner based on 
different key to ensemble and serialized RNN.

In reducer we can perform ensebling of two different deep neural nets using test dataset stored in a distributed cache.
The project look like a bit complicated but i am sure its not going to be that much complicated.
