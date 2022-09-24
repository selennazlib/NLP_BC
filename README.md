# NLP-BC
>**It's a repository that contains my all the cheatsheets and projects related to NLP.**


### RNN: Recurrent neuron is send to output back to itself.

![img](https://snipboard.io/6gSnJ1.jpg)


RNN has a issue that it can forget the important previous data . Because of that we use LSTMs(long short-term memory) . In the LSTM there are  _gate mechanism_ which can control storing, writing and reading the data. 
## Forget Gate
The forget gate decides which kind of data can be used. To decide that data goes to the sigmoid function(outputs of sigmoid -> 0 and 1) or forget the previous data. If sigmodi's output is close to 1 it means that we can use that data.

![img1](https://snipboard.io/UVl0aL.jpg)

## Input Gate
The input gate helps to update to the cell state. Also we have a tanh function in this phase. Tanh function generates values between -1 and 1 which robusts the network.

![img2](https://snipboard.io/GhtrHd.jpg)

## Output Gate
The output gate's inputs are previous inputs. And this gate finalize the next hidden layer.

![img3](https://snipboard.io/WlH0R3.jpg)


------------


## End-to-end Memory Network
Our model takes a discrete set of inputs x1, ..., xn that are to be stored in the memory, a query q, and outputs an answer a. Each of the xi , q, and a contains symbols coming from a dictionary with V words. The model writes all x to the memory up to a fixed buffer size, and then finds a continuous representation for the x and q. The continuous representation is then processed via multiple hops to output a. This allows backpropagation of the error signal through multiple memory accesses back to the input during training.
![](https://snipboard.io/cwb2Kq.jpg)







###**Input memory representation**: 
Suppose we are given an input set x1, .., xi to be stored in memory. The entire set of {xi} are converted into memory vectors {mi} of dimension d computed by embedding each xi in a continuous space, in the simplest case, using an embedding matrix A.  The query q is also embedded  to obtain an internal state u. In the embedding space, we compute the match between u and each memory mi by taking the inner product followed by a softmax:
                                          ![](https://snipboard.io/Tn5qZQ.jpg)
p is a probability vector over the inputs .

###**Output memory representation: **
Each xi has a corresponding output vector ci. The response vector from the memory o is then a sum over the transformed inputs ci , weighted by the probability vector from the input:
![](https://snipboard.io/KUDRcI.jpg)

###**Generating the final prediction:**
In the single layer case, the sum of the output vector o and the input embedding u is then passed through a final weight matrix W (of size V × d) and a softmax to produce the predicted label:
![](https://snipboard.io/Z9EWsR.jpg)

> *This notes 	are belong to Facebook AI Research New York (Arthur Szlam, Jason Weston, Rob Fergus, Sainbayar Sukhbaatar)