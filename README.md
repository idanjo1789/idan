# Color Recognition from Image

## Description
This project is a tool for recognizing and naming the colors present in an image. It leverages image processing techniques to analyze the image and identify the prominent colors. This can be useful in various applications such as design, art, and computer vision.

## Table of Contents
1. [Installation](#installation)
2. [Usage](#usage)
3. [Running Models with Learned Weights](#running-models-with-learned-weights)
4. [Model Visualizations](#model-visualizations)

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
My code is divided into 8 different model builds and one more file that runs all the models. Now I will explain about the 8 models:

### Level 1
At the beginning, there is the same encoder which facilitates the calculation later. After the same encoder, I test only the encoder.
- **File name**: `Building an auto encoder`
- **Input**: One channel
- **Output**: One channel

### Level 2
I use the encoder from step 1 and build 4 models each of which recognizes the image. It should be noted that the encoders recognize the image in HSV color representation and not RGB.
- **File names**: 
  - `Model 1 decoder construction`
  - `Model 2 decoder construction`
  - `Model 3 decoder construction`
  - `Model 4 decoder construction`
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

## Running Models with Learned Weights
After training and saving all models, use the following script to check all saved models and run them on the images in the `test` folder.
- **File name**: [`Running models with learned weights.ipynb`](Running%20models%20with%20learned%20weights.ipynb)
- **Command**: 

## Model Visualizations

### Level 1 Encoder

#### Visualization of Level 1 Encoder
![Level 1 Encoder](https://github.com/user-attachments/assets/27d8eb47-2194-481b-a2ba-542b33bbe294)

### Level 2 Encoders

#### Visualization of Model_A pth
![Model_A pth](https://github.com/user-attachments/assets/7199d9b2-60de-47b4-b235-967b521aee8e)

#### Visualization of Model_B pth
![Model_B pth](https://github.com/user-attachments/assets/d35aa197-8188-473c-955c-9ccee686d602)

#### Visualization of Model_C pth
![Model_C pth](https://github.com/user-attachments/assets/04804fff-53cb-4551-a065-53d72dccb092)

#### Visualization of Model_D pth
![Model_D pth](https://github.com/user-attachments/assets/b37bcede-d557-4412-96d3-93a344aec632)

### HSV Models

#### Visualization of Model_Hue pth
![Model_Hue pth](https://github.com/user-attachments/assets/429fa855-4764-4927-aba5-021c0a85c763)

#### Visualization of Model_Saturation pth
![Model_Saturation pth](https://github.com/user-attachments/assets/ed15ecff-de8a-4b7c-a46a-33252f0b82a2)

#### Visualization of Model_Value pth
![Model_Value pth](https://github.com/user-attachments/assets/9bd82de8-1240-442e-a628-ff774eae7f65)
