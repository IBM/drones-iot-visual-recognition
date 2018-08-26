# Drones-IoT-Visual-Recognition
Save Lives with Drones / IoT / Visual Recognition - Call for Code Hands on Lab

## Introduction

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

You can complete this task in no more than 10 minutes.

# Hands on Lab

## Step 1 - Learn about Drones

- [Contixo F8](http://www.contixo.com/products/Contixo-F8-Foldable-Pocket-Size-Selfie-Drone-Voice-Controls-720P-HD-Wifi-Live-FPV-Video-Camera-360-Stunts-8-10min-Fly-Time-Gravity-Control-Red_308.html)
- Tello - Control a [Tello Drone using Node-RED](https://github.com/johnwalicki/Node-RED-Tello-Control)
- Hobbyist drones
- Commercial drones

## Step 2 - Capturing Images
Use your drone to capture images of interesting objects that you want to train a visual recognition model to autonomously identify.

In this lab, we have created three zip files to identify neighborhoods affected by the devastating 2018 West Coast wildfires. These images will be used as our training set.
- Aerial drone images of burned homes - [BurnedHomes.zip](/classes/BurnedHomes.zip)
- Aerial drone images of intact homes - [AerialHomes.zip](/classes/AerialHomes.zip)
- Aerial drone images of forests, roads, rivers to be used for the negative class. [NotHomes.zip](/classes/NotHomes.zip)

*Source attribution: USA Today [article](https://www.usatoday.com/in-depth/news/nation-now/2018/08/02/drone-aerials-california-wildfire-devastation/889885002/), various internet sources*


## Step 3 - Watson Studio
In this section, we will create a Watson Studio account, create a Project and Watson Visual Recognition model to identify images in several classes.

- Create a Watson Studio account - follow these [instructions](/STUDIO.md)
- Create a Project
- Create a Visual Recognition model - follow these [instructions](/VISRECO.md)
- Upload three zips to Cloud Storage
- Create a class *Burned Home* - drag a zipfile
- Create another class *Intact Home* - drag a zipfile
- Create a negative class *Not Homes* - drag a zipfile
- Train your model - wait a few minutes

## Step 4 - Test your model
In this section you will use sample images to confirm your model.
- Test your model - follow these [instructions](/VRMTEST.md)

## Step 5 - Implement this model in your Application
- Code snippets

Let's get started - [Set up Watson Studio](/STUDIO.md)

*Quick links :*
[**Home**](/README.md) - [Watson Studio](/STUDIO.md) - [Visual Recognition Model](/VISRECO.md) -
[Test and Deploy](/VRMTEST.md)
