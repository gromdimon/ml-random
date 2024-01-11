# RuPoemGPT

![header](header.png)

RuPoemGPT is a reimplementation of the original [makemore](https://github.com/karpathy/makemore) project by Andrej Karpathy. This version just replicates the functionalities. Core features such as character-level language modeling and a simple neural network for generating text are preserved. Enhancements include improved model performance and additional text generation features. This project is particularly beneficial for those interested in natural language processing and serves as a practical platform for exploring text generation.

### Installation

To get started with this enhanced version of makemore, follow these steps:

1. **Fork the Repository:** Begin by forking my repository into your GitHub account. Click on the "Fork" button located at the top-right of the repository page.

2. **Clone and Set Up:** After forking, clone the repository to your local environment:

   ```bash
   git clone https://github.com/gromdimon/makemore.git
   ```

   Navigate into the cloned directory:

   ```bash
   cd makemore
   ```

   Install the required dependencies:

   ```bash
   pip install -r requirements.txt
   ```

### Example Usage

Since the real module is not available, you can use any of notebooks in the repo and run them in Google Colab. The notebooks are self-contained and include all the necessary code and instructions. All example generations are provided at the end of each notebook.

**Example:**

```python
# sample from the model
g = torch.Generator().manual_seed(2147483647 + 10)

for _ in range(20):
    
    out = []
    context = [0] * block_size # initialize with all ...
    while True:
      emb = C[torch.tensor([context])] # (1,block_size,d)
      h = torch.tanh(emb.view(1, -1) @ W1 + b1)
      logits = h @ W2 + b2
      probs = F.softmax(logits, dim=1)
      ix = torch.multinomial(probs, num_samples=1, generator=g).item()
      context = context[1:] + [ix]
      out.append(ix)
      if ix == 0:
        break
    
    print(''.join(itos[i] for i in out))
```

### License

MIT

---

Note: This project was made just for learning purposes. It is not intended to be used for any other purpose. All credit goes to Andrej Karpathy for the original makemore project.