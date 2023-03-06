# Image Classification using Vision Transformers (ViT)

This is a project for image classification using Vision Transformers (ViT) in PyTorch. The project consists of three classification tasks: quality, rotation, and mode. 

## Dataset
The Blur Dataset from Kaggle was used to train the models. The dataset can be accessed from the following link: https://www.kaggle.com/datasets/kwentar/blur-dataset. Each image is assigned to one of the classes for each of the three tasks. The quality task has three subclasses: defocused_blurred, motion_blurred, and sharp. The expected output class demands prediction of three classes for a single test image. First, the Quality, Either the Image is Blur, Torch (overexposed) or Sharp, Second, the Rotation, this class has four subclasses: 90_degrees_clockwise, 90_degrees_counterclockwise, 180_degrees, and no_rotation. Third, the mode class, Either the image is RGB and BGR. 

## Preprocessing
All images were resized to 224x224 pixels and normalized using the mean and standard deviation of the ImageNet dataset.

For the quality output class, I took 175 images from both defocused_blur and motion_blur for the training, so that the dataset would be balanced, for the torch subclass the sharp images were made overexposed on a random value between 1.5 - 2.5 with OpenCV. The sharp images were used to create the sharp subclass.

For the rotation task, images were rotated 90 degrees clockwise, 90 degrees counterclockwise, and 180 degrees using OpenCV. The original images were used to create the no_rotation subclass.

For the mode task, the sharp images were converted to BGR using OpenCV.

## Model Architecture
The ViT model used for this project is the base model with patch size 16 and input size 224. The final layer was modified to output the correct number of classes for each task. The loss function used is cross-entropy loss. 

## Training
The model was trained using PyTorch Lightning. The training process involved fine-tuning the pre-trained ViT model on the custom dataset. The dataset was split into training and validation sets, with a batch size of 8. The Quality model was trained for 16 epochs using the Adam optimizer with a learning rate of 2e-5, the validation accuracy was above 98%, The Rotation model was trained for 12 epochs, with validation accuracy above 65% and the Mode model was trained for 20 epochs, with validation accuracy above 91%.

## Results
The final Prediction Accuracy would be more than 85% (mean of all three)

## Usage
To use the trained model for image classification, follow these steps:
1. Load the saved model using `from_pretrained` function in PyTorch.
2. Load and preprocess the image using the ViTFeatureExtractor from the transformers package.
3. Make a prediction using the loaded model.

The saved models are located in three separate folders named `mode_model`, `quality_model`, and `rotation_model`. Each folder contains two files: `config.json` and `pytorch_model.bin`. 

### Papers
The following papers were referred to for this project:

- Attention is All You Need" by Vaswani et al. (2017)
- An Image is Worth 16x16 Words: Transformers for Image Recognition at Scale" by Dosovitskiy et al. (2020)
- Vision Transformers Explained" by Cunyuan et al. (2021)

### Team
```
GitHub : https://github.com/KLAU-S
```

## Conclusion
In this project, we successfully trained a ViT model for image classification on a custom dataset. The model achieved high accuracy on the validation set for each of the three tasks. The trained models can be used for image classification tasks in various applications.
