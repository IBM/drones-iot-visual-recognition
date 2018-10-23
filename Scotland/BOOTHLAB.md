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

* Create an [IBM Cloud account](https://ibm.biz/BdYVQS)
* Log into [IBM Cloud](https://console.bluemix.net/login)

## Estimated time

You can complete this task in no more than 15 minutes.

# Hands on Lab Overview

The outline below provides a high level overview of the steps included in the lab instructions.  

## Step 1 - Watson Studio

We will create a Watson Studio account, create a Project and Watson Visual Recognition model to identify images in several classes.

- Create a Watson Studio account - follow these [instructions](STUDIO.md)
- Create a Project
- Create a Visual Recognition model - follow these [instructions](VISRECO.md)
- Upload three zips to Cloud Storage
- Create a class *Castle* - drag a zipfile
- Create another class *Black House* - drag a zipfile
- Create a negative class using the *Countryside* images - drag a zipfile
- Train your model - wait a few minutes

## Step 2 - Test your model
In this section you will use sample images to confirm your model.
- Test your model - follow these [instructions](VRMTEST.md)

Let's get started - [Set up Watson Studio](STUDIO.md)

*Quick links :*
[Home](/README.md) - [**Scotland**](BOOTHLAB.md) - [Watson Studio](STUDIO.md) - [Visual Recognition Model](VISRECO.md) - [Test and Deploy](VRMTEST.md)
