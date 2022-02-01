# Purpose
I want to follow along with different sources of LSTM tutorials to better understand it myself.


# Files
## Vanilla_LSTM.ipynb: Contains Jeff Heaton's car passing a camera simulated experiment. 
A very simple vanilla LSTM that will try to predict the "color" of a "passing car".

## Stacked_LSTM.ipynb: Contains Jason Brownlee's damped sine wave simulated experiment.
An LSTM that can understand the dual time variance of a sine wave whose amplitude decreases exponentially.
I included a little matplotlib of my favorite reconstructed yhat.
### Next steps
Play around until 1000 training steps aren't overfit. Maybe reduce the number of predicted timesteps. Maybe
increase the number of input timesteps from 50 to 500. Maybe try to do the split that we did for tRNAs. Play
around with the architecture. Learn how to split the data into training and validation sets, maybe early stopping
is the key.

## CNN_LSTM.ipynb: Contains Jason Brownlee's moving square problem.
An LSTM that has a CNN on the front that works as a 2D feature extractor. This lets us optimally process 
things like videos.
### Next steps
Understand how the CNN actually works, and the ```TimeDistributed``` layer.

## Enc_Dec_LSTM.ipynb: Contains Jason Brownlee's addition prediction problem.
Good for seq2seq type problems (which is what I have I think?)