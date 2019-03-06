# Machine Learning 

## Mar. 6, 2019 

### Neural Network Architectures

**Topics:** parameter tying, recurrent neural nets, long short term memory networks, bidirectional lstm networks, convolutional networks

**Parameter Tying**

An a priori decision to require that certain connections in the network share the same weight.

## Recurrent Neural Networks

**Sequential Tasks** Some applications involve processing sequences of data (natural language, biological sequences, time-series data). As an example consider natural language.

*Examples:* Consider a task where we want to tag each word in a sentence by the part of speech (noun, verb, etc.) that it is being used as. You may also want to do sentiment analysis, which is to determine whether a sentence is positive or negative.

In dequential tasks, it may be valuable to have the network process vary-length input sequences and remember information when processing a sequence. Recurrent neural nets enable this behavior. Here are two simple approaches.

- Elman networks: Recurrent connections for from hidden units to inputs
- Jordan networks: Recurrent connections for from output units to inputs

Overall, the structure can be thought of as doing fixed-length backpropagation at every step of the network. This way, we allow th netwrok to use the information from previous elements in the sequence to help influence the decisions made about the current element.

**Long Short Term Memory (LSTM) Networks:** RNNs are well-suited to sequence data, and because they take into account recent performance, one can think of them as modeling human short-term memory. Depending on the type of problem you are faced with and the degree to which you believe early events vs late events may influence the final output, you can set the number of elements that are kept in the short term memory of the network.

See [this source](http://colah.github.io/posts/2015-08-Understanding-LSTMs/) for a nice discussion and illustrations of LSTMs. 

LSTM Netwroks have architecture for determining what informationis useful to remember / forget. They are composed of modules like this:

![](./images/lstm1.png)

The goal is to determine which information needs to be remembered and which information can be safely forgotten. Definitely read the posted source as it contains a step-by-step walkthrough of all functions within each module.

**Bidirectional LSTM Networks:**

BiLSTM Networks have provided state of the art accuracy in natural language processing tasks. It is illustrated below, but combines the previous architecture with a backward layer to analyze the sequence from both ends.

![](./images/bidlstm.png)

## Convolutional Neutal Networks

CNNs focus on local features and try to build up global features. They are well suited for tasks where the input has spatial structure (typically images or sequences). The structure is based on four keys ideas:

- Local receptive fields
- weight sharing (parameter tying)
- pooling
- multiple layers of hidden units

*Local Receptive Fields:* input features that are close to each other wihtin the context of the spatial layout of the entire input are grouped together. This process is illustrated below. 

![](./images/cnn1.png)

