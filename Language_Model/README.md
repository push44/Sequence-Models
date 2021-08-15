## Project Objectives:

<br>

<ul>
    <li>Store text data for processing using an RNN</li>
    <li>Build a character-level text generation model using an RNN</li>
    <li>Sample novel sequences in an RNN</li>
    <li>Explain the vanishing/exploding gradient problem in RNNs</li>
    <li>Apply gradient clipping as a solution for exploding gradients</li>
</ul>

### Data Preprocessing:

<ul>
    <li>There are 19909 total characters and 27 unique characters in your data. (27 because '\n' is also considered one character along with other 26 english alphabets.)</li>
    <li>char_to_ix: Python dictionary (i.e., a hash table) to map each character to an index from 0-26.</li>
    <li>ix_to_char: Python dictionary that maps each index back to the corresponding character.</li>
    <li></li>
</ul>

At each time-step, the RNN tries to predict what the next character is, given the previous characters.
<br>
Prediction at time step t is input for time step t+1.
<br>

![sampling](./images/dinos3.png)
    
Note that first input is the "dummy" vector of zeros.

<br>

We pick the next character's index according to the probability distribution specified by the output. This is important to note, if we select the most probable, the model will always generate the same result given a starting letter.