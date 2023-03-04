# Image Classification using Vision Transformers (ViT)

This is a project for image classification using Vision Transformers (ViT) in PyTorch. The project consists of three classification tasks: quality, rotation, and mode. 

## Dataset
The dataset used for this project is a custom dataset of images. Each image is assigned to one of the classes for each of the three tasks. The quality task has three subclasses: defocused_blurred, motion_blurred, and sharp. The rotation task has four subclasses: 90_degrees_clockwise, 90_degrees_counterclockwise, 180_degrees, and no_rotation. The mode task has two subclasses: RGB and BGR. 

## Preprocessing
All images were resized to 224x224 pixels and normalized using the mean and standard deviation of the ImageNet dataset.

For the quality task, images were first converted to grayscale and then to blurred and sharpened versions using OpenCV. The blurred and sharpened versions were used to create the defocused_blurred and motion_blurred subclasses, respectively. The sharp images were used to create the sharp subclass.

For the rotation task, images were rotated 90 degrees clockwise, 90 degrees counterclockwise, and 180 degrees using OpenCV. The original images were used to create the no_rotation subclass.

For the mode task, the sharp images were converted to BGR using OpenCV.

## Model Architecture
The ViT model used for this project is the base model with patch size 16 and input size 224. The final layer was modified to output the correct number of classes for each task. The loss function used is cross-entropy loss. 

## Training
The model was trained using PyTorch Lightning. The training process involved fine-tuning the pre-trained ViT model on the custom dataset. The dataset was split into training and validation sets, with a batch size of 8. The model was trained for 12 epochs using the Adam optimizer with a learning rate of 2e-5. 

## Results
The final model achieved an accuracy of over 90% on the validation set for each of the three tasks. 

## Usage
To use the trained model for image classification, follow these steps:
1. Load the saved model using `from_pretrained` function in PyTorch.
2. Load and preprocess the image using the ViTFeatureExtractor from the transformers package.
3. Make a prediction using the loaded model.

The saved models are located in three separate folders named `mode_model`, `quality_model`, and `rotation_model`. Each folder contains two files: `config.json` and `pytorch_model.bin`. 

## Conclusion
In this project, we successfully trained a ViT model for image classification on a custom dataset. The model achieved high accuracy on the validation set for each of the three tasks. The trained models can be used for image classification tasks in various applications. 