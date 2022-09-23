# NLP-BC
 It's a repository that contains my all the cheatsheets and projects related to NLP.

RNN: Recurrent neuron is send to output back to itself.

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
