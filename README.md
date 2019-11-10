# generative-text
A side project focused on generating text using a recurrent neural network

## Background
I wanted to see if I could generate a poem based on past poems I've written. A friend suggested I look into RNNs and I stumbled on [this great package](https://github.com/minimaxir/textgenrnn
)
Following the instructions there, as well as [this blog post](https://minimaxir.com/2018/05/text-neural-networks/) I was able to get pretty decent results.

I built the model in [google colab](https://colab.research.google.com/) as suggested in the blogpost. The GPU there was a lot faster than my own CPU.

## Usage
```python
# Follow the install instructions for minimaxirs project
# Clone this repo
# Change the input textfile

python3
from textgenrnn import textgenrnn

textgen = textgenrnn()
textgen.train_from_file('test_input.txt', num_epochs=1)
textgen.generate()
```
If you want to import an already generated model (created in google colab for instance), use this code.

```python
from textgenrnn import textgenrnn
textgen = textgenrnn(weights_path='colaboratory_weights.hdf5',
                       vocab_path='colaboratory_vocab.json',
                       config_path='colaboratory_config.json')
```