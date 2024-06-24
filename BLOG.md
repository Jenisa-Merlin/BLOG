# Creating Text-to-Video Workflow with ComfyUI: An In-Depth Guide

## Introduction
Hello, let me take you through a brief overview of text to video process using ComfyUI. It is recommended for new users to follow these steps outlined in this tutorial to set up the Animatediff Text-to-Video workflow and to operate them. ComfyUI lets you easily turn textual instructions into interesting videos without much time and effort. Let’s dive in!

## What is ComfyUI
ComfyUI is an effective application which aims at improving convenience when it comes to producing any form of multimedia, including videos. It has an interface that guides users in creating videos that are informative and interesting by using text-to-speech and text-to-video prompts, thus making it easier to create without necessarily having made a professional video. [Learn more about ComfyUI](https://stable-diffusion-art.com/comfyui/)

## Table of Contents
1. [Overview of the Workflow](#1-overview-of-the-workflow)
2. [Key Components](#2-key-components)
3. [Workflow](#3-workflow)
4. [Step-by-Step Workflow Setup](#4-step-by-step-workflow-setup)
5. [Best Practices](#5-best-practices)
6. [Custom Nodes](#6-custom-nodes)
7. [Models](#7-models)
8. [Troubleshooting and FAQs](#8-troubleshooting-and-faqs)
9. [Conclusion](#9-conclusion)
10. [Sample Prompt](#10-sample-prompt)
11. [Sample Output](#11-sample-output)

## 1. Overview of the Workflow
The Animatediff Text-to-Video workflow in ComfyUI allows you to generate videos based on textual descriptions. With this workflow, there are several nodes that take an input text, transform the text into frames to build the final video and output the frames as a video.

## 2. Key Components
Here are the primary components of the workflow:

- **Input Nodes**: Define parameters such as the number of frames, width, and height of the video.
- **Model Loading Nodes**: Load necessary models for image generation and processing.
- **Prompt Nodes**: Manage the text prompts that guide the video generation.
- **Animation Nodes**: Handle the frame-by-frame animation generation.
- **Output Nodes**: Compile the generated frames into a video and output the final result.

## 3. Workflow 
![Workflow Image](https://raw.githubusercontent.com/Jenisa-Merlin/BLOG/main/workflow.png)
[Download Workflow JSON](https://raw.githubusercontent.com/Jenisa-Merlin/BLOG/main/Workflow.json)

## 4. Step-by-Step Workflow Setup
Follow these steps to set up the Animatediff Text-to-Video workflow in ComfyUI:

### Step 1: Define Input Parameters
Set the basic parameters for your video:
- **Number of Frames**: In the case that the video is going to be split into different frames, type the number of frames in the “Number of Frames” node.
- **Width and Height**: Employ the respective nodes involving the X and Y axis to set the dimensions of each frame.

### Step 2: Load Necessary Models
Load the models required for generating and processing images:
- **Load Checkpoint w/ Noise Select**: Prepare the model checkpoint that will be used for the next generation frames.
- **Load VAE**: Prepare the Python environment for decoding the Variational Autoencoder (VAE) model.

### Step 3: Configure Prompts
Set up the textual prompts that will guide the video content:
- **Pre Text**: Describe the instructions that will be initially written on the screen of the video clip.
- **App Text**: Text that can appear in the video and that is not included in the script or narration but is useful to complement what is being explained on the screen.
- **Batch Prompt Schedule**: Closely monitor the flow of additional cues throughout the video and the overall timing of the prompts’ appearance.

### Step 4: Set Up Animation Nodes
Configure the nodes responsible for creating the animation:
- **Animate Diff Nodes**: Employ these nodes to provide information about how the frames are going to change and develop depending on the given text cues.
- **Context Options and Looped Uniform**: Specify where the preferred looping is to be set to make for easy progression from one step to another.

### Step 5: Generate and Compile Video
Finalize the video generation and compilation process:
- **KSampler**: Sampling the latent space to develop a rich elaborated frame.
- **VAE Decode**: Develop a method to decode these representations into visual images.
- **Animation Diff Combine**: Set the frames created earlier into a video.

## 5. Best Practices
- **Optimize Parameters**: Experiment with different parameters to find the best settings for your specific use case.
- **Modular Design**: Keep your workflow modular to facilitate easier updates and maintenance.
- **Documentation**: Document each node’s configuration for future reference and troubleshooting.

## 6. Custom Nodes
The following custom nodes are used in this workflow:
- **Animate Diff Nodes**: These nodes manage the frame-by-frame animation based on text prompts.
- **Batch Prompt Schedule**: This node helps in managing the sequence and timing of the prompts throughout the video.
- **Load Checkpoint w/ Noise Select**: Loads the model checkpoint used for generating frames with noise selection.
- **VAE Decode**: Decodes the latent representations into images.

## 7. Models
The following models are used in this workflow:
- **Load Checkpoint w/ Noise Select**: Uses a model checkpoint, such as `nangijala_final.safetensors`, which is essential for generating the video frames.
- **Load VAE**: Uses the `vae-ft-mse-840000-ema-pruned.ckpt` model, which is crucial for decoding the latent representations into images.

## 8. Troubleshooting and FAQs
### Common Issues
- **Frames Not Generating Properly**: Ensure that all model paths are correctly set and that the models are compatible with the input dimensions.
- **Video Compilation Errors**: Check the output node settings and ensure that all frames are correctly processed.

### FAQs
- **How do I update the models?**
  Regularly check for updates from the model providers and follow the update instructions specific to ComfyUI.
- **Can I customize the text prompts dynamically?**
  Yes, use the Batch Prompt Schedule node to dynamically change prompts based on the frame index or other conditions.

## 9. Conclusion
With this guide, you should now have a clear plan on how to construct your own text-to-video processes within the ComfyUI framework. This function can assist you in generating videos more easily without losing much time and possesses a lot of flexibility. Happy creating!

## 10. Sample Prompt
**Pre Text**:
(Masterpiece, best quality:1.2), full body shot,

**App Text**:
natural bright lighting, sharp, highly detailed, ultra hyperrealistic, 4k, vibrant

**Batch Prompt**:

"0" : "Young man, early 20s, sitting in college lecture hall, attentive expression",

"25" : "Man taking notes, surrounded by other students, lecture hall background",

"50" : "Man walking through college campus, backpack on, autumn scenery",

"75" : "Man enters college library, looks around curiously",

"100" : "Man browsing bookshelves, fingers tracing book spines",

"125" : "Woman enters library, carrying stack of books",

"150" : "Man and woman reach for same book, hands touch, surprised expressions",

"175" : "Close-up of man and woman's eyes meeting, soft smiles forming",

"200" : "Man and woman chatting at library table, books spread out",

"225" : "Couple walking together on campus path, golden hour lighting",

"250" : "Couple having picnic in park, laughing, feeding each other strawberries",

"275" : "Couple studying together in dorm room, comfortable closeness",

"300" : "Couple on coffee date, sitting close in cafe, holding hands",

"325" : "Couple at college party, dancing together, joyful expressions",

"350" : "Couple kissing under tree on campus, romantic mood",

"375" : "Couple in graduation gowns, holding diplomas, proud smiles",

"400" : "Couple moving into first apartment, carrying boxes together",

"425" : "Man proposing on one knee, woman surprised and emotional",

"450" : "Couple at altar, exchanging rings, surrounded by loved ones",

"475" : "Couple on honeymoon, walking on beach at sunset, holding hands",

"500" : "Couple in their new home, cuddling on couch, looking at photo album of their journey"

**Negative Prompt**:
darkness, shadow, close up, head shot, (bad quality, worst quality:1.2), NSFW, nude, noisy, blurry, deformed, black and white, bad anatomy, deformed, bad eyes, crossed eyes, disfigured, poorly drawn face, mutation, ((extra limb)), ugly, poorly drawn hands, missing limb, floating limbs, disconnected limbs, malformed hands, out of focus, long neck, long body, ((((mutated hands and fingers)))), (((out of frame ))), cropped, low-res, ugly, too many fingers, grainy, extra limbs, extra fingers, mutated hands, bad proportions, blind, ugly eyes, text, writing, logo

## 11. Sample Output
![OUTPUT](https://raw.githubusercontent.com/Jenisa-Merlin/BLOG/main/OUTPUT.gif)