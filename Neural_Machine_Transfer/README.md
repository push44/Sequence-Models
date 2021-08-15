## Project Objectives:

<ul>
    <li>We will build a Neural Machine Translation (NMT) model to translate human-readable dates ("25th of June, 2009") into machine-readable dates ("2009-06-25").</li>
    <li>We will do this using an attention model, one of the most sophisticated sequence-to-sequence models. </li>
</ul>

## Problem overview:
<ul>
    <li>The network will input a date written in a variety of possible formats (e.g. "the 29th of August 1958", "03/30/1968", "24 JUNE 1987").</li>
    <li>The network will translate them into standardized, machine readable dates (e.g. "1958-08-29", "1968-03-30", "1987-06-24"). That is we will have the network learn to output dates in the common machine-readable format YYYY-MM-DD. </li>
</ul>

We will train the model on a dataset of 10,000 human readable dates and their equivalent, standardized, machine readable dates.

### We have:

<ul>
    <li>    dataset: a list of tuples of (human readable date, machine readable date).</li>
    <li>human_vocab: a python dictionary mapping all characters used in the human readable dates to an integer-valued index.</li>
    <li>    machine_vocab: a python dictionary mapping all characters used in machine readable dates to an integer-valued index.
        <ul>
            <li>Note: These indices are not necessarily consistent with human_vocab.</li>
        </ul>
    </li>
    <li>inv_machine_vocab: the inverse dictionary of machine_vocab, mapping from indices back to characters.</li>
</ul>

Before mapping the raw text data into the index values:

<ul>
    <li>We will set Tx=30
        <ul>
            <li>We assume Tx is the maximum length of the human readable date.</li>
            <li>If we get a longer input, we would have to truncate it.</li>
        </ul>
    </li>
    <li>We will set Ty=10
        <ul>
            <li>YYYY-MM-DD" is 10 characters long.</li>
        </ul>
    </li>
</ul>

#### Example:

Source date: 9 may 1998<br>
Target date: 1998-05-09

<br><br>

Source after preprocessing (indices): [12  0 24 13 34  0  4 12 12 11 36 36 36 36 36 36 36 36 36 36 36 36 36 36
 36 36 36 36 36 36]

 <br><br>

 Target after preprocessing (indices): [ 2 10 10  9  0  1  6  0  1 10]

 ### Neural Machine Translation with Attention:

 <ul>
    <li>If we had to translate a book's paragraph from French to English, we would not read the whole paragraph, then close the book and translate.</li>
    <li>Even during the translation process, we would read/re-read and focus on the parts of the French paragraph corresponding to the parts of the English we are writing down.</li>
    <li>The attention mechanism tells a Neural Machine Translation model where it should pay attention to at any step.</li>
 </ul>

### Attention Model:

![attention_model](./images/attn_model.png)

### Attention Mechanism:
![attention_mechanism](./images/attn_mechanism.png)

The attention variables are used to compute the context variable for each timestep in the output.

<br>

There are two separate LSTMs in this model.
<br>

The post-attention LSTM at time 't' does not take the previous time step's prediction. The post-attention LSTM at time 't' only takes the hidden state and cell state as input.