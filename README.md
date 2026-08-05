# Jigsaw Puzzle Image Reconstruction

This repository contains a notebook experiment for reconstructing a 96 x 96 RGB image from nine shuffled 28 x 28 patches. The notebook downloads the STL-10 unlabeled image set, builds scrambled-patch generators, defines a mean-patch baseline, and trains a Keras reconstruction model evaluated with mean absolute error.

The model code combines a convolutional patch encoder, self-attention over patch tokens, cross-attention to a learned 3 x 3 position grid, and a convolutional upsampling decoder.

## Repository contents

- `patches_to_image_spec.ipynb` - data loading, patch generation, visualization, model definition, training, evaluation, and learning-curve cells
- `best_jigsaw_model.keras` - tracked Keras model artifact
- `jigsaw_model.keras` - tracked Keras model artifact

## Requirements

The notebook imports:

- TensorFlow and Keras
- NumPy
- Matplotlib

It also needs network access and local storage for the STL-10 download. No pinned environment or dependency file is included.

## Use

Open `patches_to_image_spec.ipynb` in a Jupyter or Google Colab environment and run the cells in order. The data-loading cell downloads and extracts STL-10 through `tf.keras.utils.get_file`.

The notebook includes saved outputs, but this README does not report performance values because the training and evaluation were not rerun during documentation review.
