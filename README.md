# Mathematical-Problem-Solving-with-Transformers

This repository contains a project focused on solving basic mathematical problems using neural networks. The project is centered around subsets of the DeepMind mathematical dataset. The goal is to build a sequence-to-sequence mapping model that can accurately answer mathematical questions.

## Table of Contents

- [About](#about)
- [Getting Started](#getting-started)
- [Dataloader](#dataloader)
- [Model](#model)
- [Greedy Search Algorithm](#greedy-search-algorithm)
- [Accuracy Computation](#accuracy-computation)
- [Training](#training)
- [Experiments](#experiments)
- [Results](#results)

## About

This project aims to solve mathematical problems using neural networks. It focuses on implementing and training a Transformer model to perform sequence-to-sequence mapping for mathematical questions and their corresponding answers.

## Getting Started

Follow these steps to set up and run the project:

1. **Download the Pre-processed Dataset:**

   Download the pre-processed dataset from [Datase](Dataset). The dataset is organized into modules, each containing `train.x` (questions) and `train.y` (answers) files.

2. **Clone the Repository:**

   Clone this repository to your local machine:

   ```sh
   git clone https://github.com/AriolaLeka/Mathematical-Problem-Solving-with-Transformers.git
   ```

3. **Dependencies:**

   Ensure you have the required dependencies installed. You can install them using:

   ```sh
   pip install -r requirements.txt
   ```

## Dataloader

The provided dataloader implementation can be found in the `dataloader` module. It automatically generates a vocabulary for the model while reading the dataset. It uses the same vocabulary for both input (source) and output (target) by default.

## Model

The project includes a Transformer encoder-decoder model. The class `TransformerModel` implements the model architecture. The model consists of an encoder and a decoder, which can be forwarded separately. The `forward` method of the model demonstrates how to use the entire transformer or separately forward the encoder and decoder.

## Greedy Search Algorithm

The greedy search algorithm is implemented to decode sequences using the trained Transformer model. The algorithm forwards the encoder once for each batch and iteratively decodes the output sequence. The search process stops based on specified stopping criteria, including reaching the end-of-sentence token or exceeding the target sequence length.

## Accuracy Computation

The `compute_accuracy` function calculates the accuracy of the model's predictions. A prediction is counted as correct only if the entire output sequence matches the correct answer sequence.

## Training

To train the model:

1. Define your hyperparameters in the `train.py` script.
2. Run the training script:

   ```sh
   python train.py
   ```

The training pipeline involves defining the loss function, input tensors, and target label tensors. Training and validation losses, as well as accuracy, are tracked during training.

## Experiments

The project includes experiments on different modules from the DeepMind mathematical dataset. You can run experiments on modules like "numbers - place value" and "compare - sort". Adjust hyperparameters and model configurations for each experiment.

## Results

After training, the model's performance can be evaluated. Use the trained model to make predictions and compare them to ground truth answers. Report and visualize training curves, accuracy, and example predictions.
