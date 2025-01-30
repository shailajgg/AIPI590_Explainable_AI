# Image Classification Explainability with LIME

## Overview

This project demonstrates how to make deep learning models more interpretable by using LIME (Local Interpretable Model-agnostic Explanations) to explain individual predictions from a pre-trained ResNet34 model. By generating visual explanations for the model's decisions, we can better understand why the model classifies images in certain ways.

## Background

Deep learning models, while powerful, often function as black boxes where their decision-making process isn't immediately clear. LIME helps address this limitation by perturbing inputs and analyzing how the model's predictions change in response. This allows us to identify which parts of an image are most influential in the model's classification decision.

## Features

The project includes functionality for:
- Loading and preprocessing images for deep learning models
- Making predictions using a pre-trained ResNet34 model
- Generating LIME explanations for individual predictions
- Visualizing the parts of images that most influenced the model's decisions
- Comparing original images with their explanations
- Supporting both positive and negative feature contributions

## Requirements

The following Python packages are required:
```
torch
torchvision
numpy
lime
scikit-image
pillow
matplotlib
```

You can install all dependencies using:
```bash
pip install -r requirements.txt
```

## Installation

1. Clone this repository:
```bash
git clone https://github.com/yourusername/image-classification-explainability.git
cd image-classification-explainability
```

2. Install the required packages:
```bash
pip install -r requirements.txt
```

3. Download the ImageNet class labels file:
```bash
wget https://raw.githubusercontent.com/anishathalye/imagenet-simple-labels/master/imagenet-simple-labels.json
```

## Usage

The project can be used in two ways:

### 1. Using the Jupyter Notebook

The notebook provides a step-by-step walkthrough of the process:
```bash
jupyter notebook Image_Classification_Explainability.ipynb
```

### 2. Using the Python Script

Run the script directly with your image:
```bash
python explain_classification.py --image_path your_image.jpg
```

## How It Works

The explanation process follows these steps:

1. Image Preprocessing: The input image is resized and normalized according to ImageNet standards.

2. Initial Prediction: The ResNet34 model makes its initial classification of the image.

3. LIME Analysis: The explainer:
   - Divides the image into interpretable components (superpixels)
   - Creates variations of the image by hiding different combinations of superpixels
   - Observes how the model's predictions change with these variations
   - Identifies which regions most strongly influence the prediction

4. Visualization: The results are displayed showing:
   - The original image
   - An overlay highlighting important regions
   - Green regions that positively influenced the prediction
   - Red regions that negatively influenced the prediction

## Example Output

The script generates visualizations showing:
- Left: Original input image
- Right: LIME explanation overlay showing influential regions

## Advanced Usage

You can customize the explanation process by modifying parameters:
```python
explanation = explainer.explain_instance(
    image_array,
    classifier_fn,
    top_labels=5,          # Number of top predictions to explain
    hide_color=0,          # Color used for perturbations
    num_samples=1000       # Number of perturbation samples
)
```

## Limitations

- Computation time increases with the number of samples
- Results may vary slightly between runs due to random sampling
- Quality depends on the effectiveness of superpixel segmentation
- Explanations are local and may not generalize to other images

