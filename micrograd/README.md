# micrograd+

![awww](puppy.jpg)

A tiny Autograd engine (with a bite! :)). This project is a modified version of the original micrograd project by Andrej Karpathy. I have overridden and extended some functionalities to suit my specific needs. The core features, such as backpropagation (reverse-mode autodiff) over a dynamically built DAG and a small neural networks library, remain intact. The modifications I made include additional operations and enhancements to the existing codebase. This project can still be useful for educational purposes and serves as a lightweight framework for understanding autograd.

### Installation

```bash
pip install micrograd
```

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

For added convenience, the notebook `trace_graph.ipynb` produces graphviz visualizations. The modified version includes enhanced visualization capabilities. By calling the `draw_dot` function on a specific part of the code, it generates a graph that shows both the data (left number in each node) and the gradient (right number in each node). This visualization helps in understanding the flow of computations and gradients within the network.

### Running tests

To run the unit tests, you may need to install additional dependencies based on the modifications I made. Please refer to the project documentation for detailed instructions. Once the dependencies are installed, you can run the tests by executing the following command:

```bash
python -m pytest
```

### License

MIT

---

Note: The above Readme is a modified version of the original micrograd project's Readme by Andrej Karpathy. The modifications were made to reflect the changes and additions I made in my overridden version of the project.
