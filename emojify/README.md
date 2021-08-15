## Project Objectives:

<ul>
    <li>Create an embedding layer in Keras with pre-trained word vectors</li>
    <li>Explain the advantages and disadvantages of the GloVe algorithm</li>
    <li>Describe how negative sampling learns word vectors more efficiently than other methods</li>
    <li>Build a sentiment classifier using word embeddings</li>
    <li>Build and train a more sophisticated classifier using an LSTM</li>
</ul>

In the emojifier-V1 model we output (m, 1) shaped vector for the 'm' text samples. To do this we average over the word embedding representation of the sentences. And then use softmax after multiplying average vector with 'W' vector.

<br>

The major drawback of using this method is that word order is not taken into the consideration. Hence, emojify-V1 will perform poorly on sentences such as "This movie is not good and not enjoyable".

<br>

In emojifier-V2, we are going to build an LSTM model that takes word sequences as input! This model will be able to account for word ordering. <br>

Emojifier-V2 will continue to use pre-trained word embeddings to represent words. But we will feed word embeddings into an LSTM, and the LSTM will learn to predict the most appropriate emoji.

![emojify-v2](./images/emojifier-v2.png)

