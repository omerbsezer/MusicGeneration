# Music Generation

With trained DL model (LSTM), new sequences of time series data can be predicted. In this project, it will be implemented a model which inputs a sample jazz music and samples/generates a new music. Code is adapted from Andrew Ng's Course 'Sequential models'.

## Input File and Parameters
Model is trained with "data/original_music"
* "X, Y, n_values, indices_values = load_music_utils()"
* Number of training examples: 60,
* Each of training examples length of sequence:30
* Our music generation system will use 78 unique values. 

* X: This is an (m,  Tx , 78) dimensional array. We have m training examples, each of which is a snippet of  Tx=30Tx=30  musical values. At each time step, the input is one of 78 different possible values, represented as a one-hot vector. Thus for example, X[i,t,:] is a one-hot vector representating the value of the i-th example at time t.
* Y: This is essentially the same as X, but shifted one step to the left (to the past). 
* n_values: The number of unique values in this dataset. This should be 78.
* indices_values: python dictionary mapping from 0-77 to musical values.

## LSTM Model
LSTM model structure is:

<img width="1163" alt="music_generation" src="https://user-images.githubusercontent.com/10358317/44003036-cde60b9a-9e54-11e8-88d4-88d8c9ad0144.png">

Model is implemented with "djmodel(Tx, n_a, n_values)" function.

## Predicting and Sampling
Adding model, predicting and sampling feature, model structure is: 

<img width="1171" alt="music_gen" src="https://user-images.githubusercontent.com/10358317/44003040-d8f6335c-9e54-11e8-9260-ce930c271437.png">

Music Inference Model is similar trained model and it is implemented with "music_inference_model(LSTM_cell, densor, n_values = 78, n_a = 64, Ty = 100)" function. Music is generated with "redict_and_sample" function.
Finally, your generated music is saved in output/my_music.midi.

## References
