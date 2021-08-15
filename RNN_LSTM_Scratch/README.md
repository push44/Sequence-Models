## Project Objective:
<br>
<ul>
    <li>Define notation for building sequence models</li>
    <li>Describe the architecture of a basic RNN</li>
    <li>Identify the main components of an LSTM</li>
    <li>Implement backpropagation through time for a basic RNN and an LSTM</li>
    <li>Give examples of several types of RNN</li>
</ul>
<br>
Recurrent Neural Networks (RNN) are very effective for Natural Language Processing and other sequence tasks because they have "memory." They can read inputs $x^{\langle t \rangle}$ (such as words) one at a time, and remember some contextual information through the hidden layer activations that get passed from one time step to the next. This allows a unidirectional (one-way) RNN to take information from the past to process later inputs. A bidirectional (two-way) RNN can take context from both the past and the future

## 1 - Forward Propagation for the Basic Recurrent Neural Network

<br>
In this example, $T_x = T_y$.

![rnn](./images/RNN.png)

## RNN Cell

![rnn_cell](./images/rnn_step_forward_figure2_v3a.png)

## RNN Forward Pass

![rnn_forward_pass](./images/rnn_forward_sequence_figure3_v3a.png)

## 2 - Long Short-Term Memory (LSTM) Network

### LSTM Cell

![rnn_forward_pass](./images/LSTM_figure4_v3a.png)




