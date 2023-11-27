# ML-Random: Reimplementation of Machine Learning Projects

![Photo by <a href="https://unsplash.com/@possessedphotography?utm_content=creditCopyText&utm_medium=referral&utm_source=unsplash">Possessed Photography</a> on <a href="https://unsplash.com/photos/asimo-robot-doing-handsign-g29arbbvPjo?utm_content=creditCopyText&utm_medium=referral&utm_source=unsplash">Unsplash</a>](assets/header.jpg)


## Introduction

Welcome to ML-Random, a repository dedicated to the reimplementation of various machine learning and AI algorithms. This project aims to learn and explore different techniques, optimize existing solutions, and experiment with new ideas in the field of machine learning and AI.


## Table of Contents
1. [Project Overview](#project-overview)
2. [Technologies Used](#technologies-used)
3. [Getting Started](#getting-started)
4. [License](#license)
5. [Contact](#contact)


## Project Overview

In this repository, we focus on reimplementing a range of machine learning projects, ranging from foundational algorithms to contemporary AI solutions. The goal is to deepen our understanding of these algorithms, improve upon them, and share insights with the broader community.

### Projects Included:
- Mikrograd: [A minimal autograd engine based on micrograd of Andrej Karpathy]
- Makemore: [A tool for generating synthetic data. Based on the work of Andrej Karpathy]
- ...


## Technologies Used

- **Python**: The primary programming language used for implementing algorithms.
- **Libraries/Frameworks**: PyTorch, Scikit-learn, Matplotlib.


## Getting Started

These instructions will help you set up the project on your local machine for development and testing purposes.

### Prerequisites

Ensure you have `pyenv` and `pipenv` installed on your system. If not, follow these steps:

- Install `pyenv`:
  ```
  curl https://pyenv.run | bash
  ```

- Install `pipenv`:
  ```
  pip install pipenv
  ```

### Installation

Follow these steps to get your development environment running:

1. Clone the repository:
   ```
   git clone https://github.com/gromdimon/ml-random.git
   ```

2. Navigate to the project directory:
   ```
   cd ml-random
   ```

3. Set the local Python version using `pyenv`:
   ```
   pyenv install 3.10.12
   pyenv local 3.10.12
   ```

4. Install `pipenv` for the local Python version:
   ```
   pip install --user pipenv
   ```

5. Install dependencies using `pipenv`:
   ```
   pipenv install
   ```

6. Activate the `pipenv` environment:
   ```
   pipenv shell
   ```

### Project-Specific Instructions

Each project within this repository may have additional setup or instructions. Please refer to the README.md file within each project's directory for more specialized guidance.


## License

Distributed under the MIT License. See `LICENSE` for more information.
