# Picograd

![awww](puppy.jpg)

A tiny ~~Micrograd~~ Picograd engine. This project is a modified version of the original [micrograd](https://github.com/karpathy/micrograd/tree/master) project by Andrej Karpathy. I have overridden and extended some functionalities. The core features, such as backpropagation (reverse-mode autodiff) over a dynamically built DAG and a small neural networks library, remain intact. The modifications I made include additional operations and enhancements to the existing codebase. This project can still be useful for educational purposes and serves as a lightweight framework for understanding picograd.

### Installation

To install and use this modified version of micrograd, follow these steps:

1. **Fork the Repository:** Start by forking my repository to your own GitHub account. You can do this by clicking the "Fork" button at the top-right corner of the repository page.

2. **Download Dependencies:** After forking the repository, clone it to your local machine using the following command:

   ```bash
   git clone https://github.com/Your-Username/micrograd.git
   ```

   Next, navigate to the cloned repository:

   ```bash
   cd micrograd
   ```

   Now, download the required dependencies by running the following command:

   ```bash
   pip install -r requirements.txt
   ```

   This will install the necessary dependencies for the project.

3. **Use Models from the `engine` Folder:** In this modified version, you can use the models provided in the `engine` folder. The main models you can import and use are:

   - `Value`: Represents a scalar value that can be used in computations.
   - `Neuron`: Represents a single neuron.
   - `Layer`: Represents a layer of neurons.
   - `MLP`: Represents a multi-layer perceptron (neural network) built using the `Layer` class.

   You can import these models in your code by using the following import statements:

   ```python
   from engine.value import Value
   from engine.mlp import Neuron, Layer, MLP
   ```

   Once imported, you can utilize these models to build and train your own neural networks.

### Example usage

Below is a slightly contrived example showing a number of possible supported operations, including the additional operations I implemented:

```python
from micrograd.engine import Value

a = Value(-4.0)
b = Value(2.0)
c = a + b
d = a * b + b**3
c += c + 1
c += 1 + c + (-a)
d += d * 2 + (b + a).relu()
d += 3 * d + (b - a).relu()
e = c - d
f = e**2
g = f / 2.0
g += 10.0 / f
print(f'{g.data:.4f}') # prints the outcome of this forward pass
g.backward()
print(f'{a.grad:.4f}') # prints the numerical value of dg/da
print(f'{b.grad:.4f}') # prints the numerical value of dg/db
```

### Training a neural net

The notebook `demo.ipynb` provides a full demo of training a 2-layer neural network (MLP) binary classifier. The modified neural network is initialized from the `micrograd.nn` module. The training process involves implementing a custom loss function, such as a simple svm "max-margin" binary classification loss, and using SGD for optimization. The modified version allows for more flexible network architectures and different loss functions. As shown in the notebook, using a 2-layer neural net with two 16-node hidden layers, we can achieve various decision boundaries on different datasets.

### Tracing / visualization

For added convenience, by calling the `draw_dot` function on a specific part of the code, you can generates a graph that shows both the data (left number in each node) and the gradient (right number in each node). This visualization helps in understanding the flow of computations and gradients within the network.

### Temporary notebooks

The `temp*.ipynb` notebooks are a temporary notebooks that I used to learn, build and test functions. It is not required for the project, but I have included it for reference.

### License

MIT

---

Note: The above Readme is a modified version of the original micrograd project's Readme by Andrej Karpathy. The modifications were made to reflect the changes and additions I made in my overridden version of the project.
