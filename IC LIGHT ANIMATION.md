# IC Light Animation

## Table of Contents
- [About the Workflow](#about-the-workflow)
- [Key Features](#key-features)
- [Overview](#overview)
- [How to Use This Workflow](#how-to-use-this-workflow)
- [Image to Image](#image-to-image)
- [Image to Video](#image-to-video)
- [Custom Nodes](#custom-nodes)
- [Models](#models)
- [Workflow](#workflow)

## About the Workflow
This workflow leverages the innovative use of AI to control and manipulate light in images. By using advanced techniques, we can relight any image, offering a range of lighting options to enhance visual appeal and context. The process involves using a shape mask to control the direction and intensity of the light, and the model is capable of handling animations as well.

## Key Features

- **Relighting Images**: Modify the lighting conditions of any image.
- **Custom Light Source**: Specify the type of light source using prompts (e.g., moonlight, sunlight, neon light).
- **Adjustable Intensity**: Control the intensity of the light to suit your needs.
- **Directional Lighting**: Adjust the direction of the light (e.g., left, right, top, bottom).
- **Lighting Types**: Choose from various lighting types such as spotlight or sunset.
- **Animation Support**: Apply these lighting effects to animations for dynamic lighting changes.

## Overview

![WORKFLOW](https://github.com/Jenisa-Merlin/IC-LIGHT-ANIMATION/blob/main/WORKFLOW.png)

## How to Use This Workflow
1. **Software Setup**: Use software like ComfyUI to install necessary nodes and models.
2. **Image Input**: Start by inputting the image you want to relight.
3. **Lighting Preferences**: Apply lighting preferences through prompts, specifying:
    - Type of light (e.g., moonlight, sunlight, neon light)
    - Intensity of the light
    - Direction of the light (e.g., left, right, top, bottom)
4. **Shape Mask**: Utilize a shape mask to control the direction and intensity of the light.
5. **Model Processing**: The model processes the image based on the specified lighting preferences.
6. **Output**: The final image with the adjusted lighting conditions is generated.

## Image to Image

![input](JARVISLAB/DAY%204/MULTI%20IMG%20GIRL.jpg)
![output](JARVISLAB/DAY%204/OUTPUT%20MULTIPLE%20IMG.png)

## Image to Video

Here are examples of converting images to videos:

![input](JARVISLAB/DAY%204/buddha.png)
![output](OUTPUT%20buddha.gif)

## Custom Nodes

### Custom Nodes Overview

Here is a summary of the custom nodes used in this workflow:

- **ComfyUI**
  - VAEEncode (2)
  - MaskToImage (1)
  - CheckpointLoaderSimple (1)
  - LoadImage (1)
  - PreviewImage (1)
  - VAEDecode (1)
- **ComfyUI Essentials**
  - ImageResize+ (1)
- **ComfyUI-ELLA-wrapper**
  - diffusers_model_loader (1)
- **ComfyUI-VideoHelperSuite**
  - VHS_DuplicateImages (1)
  - VHS_VideoCombine (2)
- **IC-Light-ComfyUI-Node**
  - LoadICLightUnetDiffusers (1)
  - iclight_diffusers_sampler (1)
- **KJNodes for ComfyUI**
  - RemapMaskRange (1)
  - GrowMaskWithBlur (1)
  - CreateShapeMaskOnPath (1)
  - SplineEditor (1)
  - ImageConcanate (1)

## Models

### Checkpoints

- **juggernaut_aftermath.safetensors**: Checkpoint for model training.

### LoRAs

- No LoRAs available for this workflow.

## Workflow

Here is the JSON file containing the workflow setup:

- [IC LIGHT ANIMATION WORKFLOW](JARVISLAB/DAY%204/IC%20LIGHT%20ANIMATION%20WORKING.json)
