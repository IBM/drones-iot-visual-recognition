# Drones-IoT-Visual-Recognition
Save Lives with Drones / IoT / Visual Recognition - Hands on Lab

## Introduction

This hands on lab uses drone aerial images, Watson Studio and Watson Visual Recognition to survey flood damaged neighborhoods, identify homes with survivors on rooftops and detect rescue boats. A lifesaving scenario might be to use drones to identify flood survivors and direct rescue boats to the victims using GPS and visual recognition.

![Watson Studio screenshot](screenshots/WatsonStudio-VisualRecognitionModelTestResults.png)

## Learning objectives

After completing this tutorial you will be able to:

* Create a Visual Recognition model in Watson Studio running in IBM Cloud
* Capture images from a drone and zip them into a class (provided)
* Train a model to identify objects in the images
* Score the identified objects

## Prerequisites

This tutorial can be completed using an IBM Cloud Lite account.

* Create an [IBM Cloud account](https://cloud.ibm.com/registration)
* Log into [IBM Cloud](https://cloud.ibm.com/login)

## Estimated time

You can complete this task in no more than 45 minutes.

# Hands on Lab Overview

The outline below provides a high level overview of the steps included in the lab instructions.  

## Step 1 - Learn about Drones

There are many types of drones available that range from toys to industrial use cases.  Many of the drones now include a camera that can store or stream aerial video to the ground. Using the livestream video frames, we can sample frames and send the images to Watson Visual Recognition for classification.
- Pocket toy drones
- Hobbyist drones
- Commercial drones

For this lab, we are not flying the drone indoors or venturing out into a field.  If you are interested in purchasing a drone, the instructors can share some of their drone experiences and recommendations.

## Step 2 - Capturing Images

One of the fun experiences of flying a drone is capturing video or pictures from a unique aerial perspective. You can use your drone to capture images of interesting objects that you want to train a visual recognition model to autonomously identify.

In this lab, we have created four zip files of pictures recorded by drones. The lab will use these images to identify neighborhoods affected by devastating flooding during Harvey, Katrina, upper MidWest and around the world. These images will be used as our training set.
- Grab them all [here](classes)
- Aerial drone images of flooded neighborhoods - [flooded-neighborhood.zip](classes/flooded-neighborhood.zip)
- Aerial drone images of flooded homes with survivors on rooftops - [rooftop-survivors.zip](classes/rooftop-survivors.zip)
- Aerial drone images of rescue boats navigating flooded landscapes - [rescueboats.zip](classes/rescueboats.zip)
- Aerial drone images of unaffected suburban neighborhoods to be used for the negative class - [suburban-neighborhood.zip](classes/suburban-neighborhood.zip)

## Step 3 - Watson Studio

In this section, we will create a Watson Studio account, create a Project and Watson Visual Recognition model to identify images in several classes.  Skip ahead if prior STSA Hands On Labs covered these initial steps.

- Create a Watson Studio account - follow these [instructions](STUDIO.md)
- Create a Project
- Create a Visual Recognition model - follow these [instructions](VISRECO.md)
- Upload four zip files to Cloud Object Storage
- Create a class *Flooded neighborhood* - drag a zipfile
- Create another class *Rooftop Survivors* - drag a zipfile
- Create another class *Rescue Boat* - drag a zipfile
- Create a negative class using the *Suburban neighborhood* images - drag a zipfile
- Train your model - wait a few minutes

## Step 4 - Test your model
In this section you will use sample images to confirm your model.
- Test your model - follow these [instructions](VRMTEST.md)

## Step 5 - Implement this model in your Application

- Embed your model into an application using these code snippets

Let's get started - [Set up Watson Studio](STUDIO.md)

*Quick links :*
[Home](/README.md) - [**Flooding**](FLOODING.md) - [Watson Studio](STUDIO.md) - [Visual Recognition Model](VISRECO.md) - [Test and Deploy](VRMTEST.md)
