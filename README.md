# GPT2

Train your own GPT2 model on predicting next characters. The code is structured in the following way:
* `dataset.py`: Contains a function for creating and preparing the dataset.
* `gpt.py`: Contains template classes for the Encoder, Decoder, Discriminator and the overall Adversarial Autoencoder.
* `train.py`: Contains the overall procedure of assignment, it parses terminal commands by user, then it sets the hyper-parameters, load dataset, initialize the model, set the optimizers and then
  it trains the adversarial auto-encoder and saves the network generations for each epoch.   
* `unittests.py`: Contains unittests for the Encoder, Decoder, Discriminator networks. 

The main pieces are:
* In `gpt.py`, the `forward` function implements the `CausalSelfAttention` block, related to the calculation of attention weights. The generate function of the GPT model is also implemented here. This function is used to forward some initial text through the model, sample from the output distribution and converts the indices back to text.
  
Default hyper-parameters are provided in the `ArgumentParser` object of the respective training functions. Feel free to play around with those to familiarize yourself with the effect of different hyper-parameters. 
The training time for descent performance, with the default hyper-parameters and architecture, is less than 30 minutes on a NVIDIA GTX1080Ti.

The `generate.py` file can be used to load pretrained gpt2 weights and generate sentences based on some context. One can play with the parameters.

## Datasets
The GPT2 is evaluated in text prediction of document collection present in `assets` folder.
