# Neural-Generator
Neural-generator is an implementation, showcasing a WaveNet-inspired extension built upon a Multilayer Perceptron (MLP) for character-level language modeling. The project focuses on generating text based on a given dataset of words, training the model to predict the next character in a sequence. The trained model allows the generation of new text based on the learned patterns from the dataset. Sample text generations demonstrate the model's ability to create coherent sequences of characters. For instance, we can feed it a dataset of names, and it will come up with some unique ideas for names that don't already exist but sound like names.

## Model implementations
### [MLP](https://www.jmlr.org/papers/volume3/bengio03a/bengio03a.pdf)
  
<img src="https://github.com/athrv/neural-generator/assets/65921445/6c5dd1dd-60e1-42a6-8a77-fb48c52f14fe" width="425" height="350"> </br>

### [WaveNet](https://arxiv.org/abs/1609.03499)
  
<img src="https://github.com/athrv/neural-generator/assets/65921445/9461ac2c-7667-4ea0-a97f-a6a6468b2f62" height="230" width="675"/> </br>

## Input
The included names.txt dataset, as an example, has the most common 32K names. 
```
emma
olivia
ava
isabella
sophia
charlotte
...
```
## Output
Some unique baby names that get eventually generated with the current test logprob of ~1.99:
```
stephania.
yeslee.
manaswi.
jeniyah.
adalie.
christell.
...
```

## Performance improvements
Original Network with MLP(3 character context + 200 hidden neurons, 12K params): training - 2.058, validation - 2.105  
Increasing context length(3 -> 8, 22K params): training - 1.918, validation - 2.027  
Implementation of WaveNet(22K params): training - 1.941, validation - 2.029  
Batchnorm buf fix: training - 1.912, validation - 2.022  
Scaling up the network(n_embd 24, n_hidden 128 (76K params)): training - 1.769, validation 1.993  
