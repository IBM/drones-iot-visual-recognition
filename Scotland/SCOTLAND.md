# Drones-IoT-Visual-Recognition
Save Lives with Drones / IoT / Visual Recognition - Call for Code Hands on Lab

## Introduction

This hands on lab uses drone aerial images, Watson Studio and Watson Visual Recognition to survey Scottish Countryside and identify Castles and traditional earthen / grass covered Black Houses.

![Watson Studio  screenshot](screenshots/WatsonStudio-VisualRecognitionModelTestResults.png)

## Learning objectives

After completing this tutorial you will be able to:

* Create a Visual Recognition model in Watson Studio running in IBM Cloud
* Capture images from a drone and zip them into a class
* Train a model to identify objects in the images
* Score and count the identified objects

## Prerequisites

This tutorial can be completed using an IBM Cloud Lite account.

* Create an [IBM Cloud account](https://console.bluemix.net/registration)
* Log into [IBM Cloud](https://console.bluemix.net/login)

## Estimated time

You can complete this task in no more than 15 minutes.

# Hands on Lab Overview

The outline below provides a high level overview of the steps included in the lab instructions.  

## Step 1 - Learn about Drones

There are many types of drones available that range from toys to industrial use cases.  Many of the drones now include a camera that can store or stream aerial video to the ground. Using the livestream video frames, we can sample frames and send the images to Watson Visual Recognition for classification.
- Pocket toy drones
  - [Contixo F8](http://www.contixo.com/products/Contixo-F8-Foldable-Pocket-Size-Selfie-Drone-Voice-Controls-720P-HD-Wifi-Live-FPV-Video-Camera-360-Stunts-8-10min-Fly-Time-Gravity-Control-Red_308.html)
- Tello - Control a [Tello Drone using Node-RED](https://github.com/johnwalicki/Node-RED-Tello-Control)
- Hobbyist drones
- Commercial drones

For this lab, we are not flying the drone indoors or venturing out into a field.  If you are interested in purchasing a drone, the instructors can share some of their drone experiences and recommendations.

## Step 2 - Capturing Images

One of the fun experiences of flying a drone is capturing video or pictures from a unique aerial perspective. You can use your drone to capture images of interesting objects that you want to train a visual recognition model to autonomously identify.

In this lab, we have created three zip files of pictures recorded by drones. The lab will use these images to identify Scottish Countryside Castles and Black Houses. These images will be used as our training set - we'll download them later.
- Aerial drone images of Castles - [Castles.zip](classes/Castles.zip)
- Aerial drone images of Black Houses - [BlackHouses.zip](classes/BlackHouses.zip)
- Aerial drone images of Scottish Countryside to be used for the negative class - [Countryside.zip](classes/Countryside.zip)

## Step 3 - Watson Studio

In this section, we will create a Watson Studio account, create a Project and Watson Visual Recognition model to identify images in several classes.

- Create a Watson Studio account - follow these [instructions](STUDIO.md)
- Create a Project
- Create a Visual Recognition model - follow these [instructions](VISRECO.md)
- Upload three zips to Cloud Storage
- Create a class *Castle* - drag a zipfile
- Create another class *Black House* - drag a zipfile
- Create a negative class using the *Countryside* images - drag a zipfile
- Train your model - wait a few minutes

## Step 4 - Test your model
In this section you will use sample images to confirm your model.
- Test your model - follow these [instructions](VRMTEST.md)

## Step 5 - Implement this model in your Application

- Embed your model into an application using these code snippets

Let's get started - [Set up Watson Studio](STUDIO.md)

*Quick links :*
[Home](/README.md) - [**Scotland**](SCOTLAND.md) - [Watson Studio](STUDIO.md) - [Visual Recognition Model](VISRECO.md) - [Test and Deploy](VRMTEST.md)
