# RuPoemGPT

![header](header.png)

RuPoemGPT is a reimplementation of the original [nanoGPT](https://github.com/karpathy/nanoGPT) project by Andrej Karpathy. This repository contains Jupyter notebooks and some python scripts used for model reconstructure and training. Core features such as character-level language modeling and a simple neural network for generating text are preserved. The core difference lies in the dataset, the model was trained on - the collection of russian poems was used. This project is particularly beneficial for those interested in natural language processing and serves as a practical platform for exploring text generation.

### Example Usage

A real usage example of the existing model will be described soon. Currently it's in development mode.

**Example:**

```sh
(ml-random) gromdimon@Dzmitrys-MacBook-Air pushgpt % python3 run.py
Loading model...
Config: vocab_size=165 batch_size=32 block_size=64 max_iters=6000 eval_interval=100 learning_rate=0.001 device='cpu' eval_iters=200 n_embd=64 n_head=8 n_layer=8 dropout=0.0
Model loaded in 0.08s
	Рато таинслие,
Завес прошла, я, обирать.

Судьба одемно того,
И сердце б болезним моим своевом?
...
...
Generation completed in 14.09s
```

```sh
(ml-random) gromdimon@Dzmitrys-MacBook-Air pushgpt % python3 train.py
0.423845 M parameters
Data loaded in 0.37s
Config: vocab_size=165 batch_size=32 block_size=64 max_iters=6000 eval_interval=100 learning_rate=0.001 device='cpu' eval_iters=200 n_embd=64 n_head=8 n_layer=8 dropout=0.0
Training started...
step 0: train loss 5.2604, val loss 5.2615
Iteration 0 completed in 14.95s
step 100: train loss 2.8156, val loss 2.7968
step 200: train loss 2.6828, val loss 2.6743
step 300: train loss 2.6191, val loss 2.6073
step 400: train loss 2.5679, val loss 2.5474
step 500: train loss 2.5202, val loss 2.5032
step 600: train loss 2.4764, val loss 2.4627
step 700: train loss 2.4259, val loss 2.4117
step 800: train loss 2.3789, val loss 2.3715
step 900: train loss 2.3309, val loss 2.3221
step 1000: train loss 2.2853, val loss 2.2777
step 1100: train loss 2.2517, val loss 2.2353
step 1200: train loss 2.1999, val loss 2.1923
step 1300: train loss 2.1567, val loss 2.1511
step 1400: train loss 2.1300, val loss 2.1328
step 1500: train loss 2.1104, val loss 2.1155
step 1600: train loss 2.0869, val loss 2.0879
step 1700: train loss 2.0511, val loss 2.0567
step 1800: train loss 2.0356, val loss 2.0503
step 1900: train loss 2.0190, val loss 2.0306
step 2000: train loss 1.9988, val loss 2.0071
Iteration 2000 completed in 513.95s
```

### Development

To run the project locally, you need to install the dependencies and run the main script. Alternatively, you can run jupyter notebooks.


### License

MIT

---

Note: This project was made just for learning purposes. It is not intended to be used for any other purpose. All credit goes to Andrej Karpathy for the original makemore project.
