# Color Recognition from Image

## Description
This project is a tool for recognizing and naming the colors present in an image. It leverages image processing techniques to analyze the image and identify the prominent colors. This can be useful in various applications such as design, art, and computer vision.

## Table of Contents
1. [Installation](#installation)
2. [Usage](#usage)


## Installation
To install and run the project locally, follow these steps:

1. Ensure you have the necessary dependencies installed (e.g., `torch`, `torchvision`, `matplotlib`, `Pillow`).

2. Create the following folders in the project directory:
    - `train`
    - `test`
    - `validation`

    These folders should contain the images for training, testing, and validation respectively. Each image should have a minimum size of 128x128 pixels.

3. Place your images in the corresponding folders:
    - `train`: Images for training the model.
    - `test`: Images for testing the model.
    - `validation`: Images for validating the model's performance.

## Usage
My code is divided into 8 different model builds and one more file that runs all the models.
Now I will explain about the 8 models:

### Level 1
At the beginning, there is the same encoder which facilitates the calculation later. After the same encoder, I test only the encoder.
- **File name**: `Building an auto encoder`
- **Input**: One channel
- **Output**: One channel

![model_encoder_trained pth](https://github.com/user-attachments/assets/ecd29ea1-85a2-4e34-9104-7959785efa5d)


### Level 2
I use the encoder from step 1 and build 4 models each of which recognizes the image. It should be noted that the encoders recognize the image in HSV color representation and not RGB.
- **File names**: 
  - `Model 1 encoder construction`
  - `Model 2 encoder construction`
  - `Model 3 encoder construction`
  - `Model 4 encoder construction`
- **Input**: Output from the encoder
- **Output**: 3 channels in HSV

### Step 3
I check the output of my 4 models and divide the output into 3 HSV channels. From there, I build 3 Hue, Saturation, and Value models each of which produces only one channel.
- **File names**: 
  - `Building the Hue model`
  - `Building the Saturation model`
  - `Building the Value model`
- **Input**: 4 channels from each model
- **Output**: One channel

### Input Requirements
The project requires the following folder structure:
- `train`: Images for training the model.
- `test`: Images for testing the model.
- `validation`: Images for validating the model's performance.

Each image should be at least 128x128 pixels.

### Saving Models
After running each script, the trained models are saved automatically.

### Running Models with Learned Weights
After training and saving all models, use the following script to check all saved models and run them on the images in the `test` folder.
- **File name**: `Running models with learned weights`
- **Command**:
