# Drones-IoT-Visual-Recognition
Save Lives with Drones / IoT / Visual Recognition - Hands on Lab / Workshop

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

In this section, we will create a Watson Studio account, create a Project and Watson Visual Recognition model to identify images in several classes.

- Create a Watson Studio account
- Create a Project
- Create a Visual Recognition model
- Upload four zip files to Cloud Object Storage
- Create a class *Flooded neighborhood* - drag a zipfile
- Create another class *Rooftop Survivors* - drag a zipfile
- Create another class *Rescue Boat* - drag a zipfile
- Create a negative class using the *Suburban neighborhood* images - drag a zipfile
- Train your model - wait a few minutes

## Step 4 - Test your model
In this section you will use sample images to confirm your model.
- Test your model

## Step 5 - Implement this model in your Application

- Embed your model into an application using these code snippets

***
<div style="page-break-after: always;"></div>
# Watson Studio Set up and Configuration in IBM Cloud

## Chapter Objectives

In this chapter you will set up Watson Studio with a new Project.  You will learn:

- Watson Studio
- How to set up a new Watson Studio Project

### Introduction

Watson Studio accelerates the machine and deep learning workflows required to infuse AI into your business to drive innovation. It provides a suite of tools for data scientists, application developers and subject matter experts, allowing them to collaboratively connect to data, wrangle that data and use it to build, train and deploy models at scale. Successful AI projects require a combination of algorithms + data + team, and a very powerful compute infrastructure.

- Learn more from the Experts - [Introducing IBM Watson Studio](https://medium.com/ibm-watson/introducing-ibm-watson-studio-e93638f0bb47)

### Watson Studio Setup

#### Log into Watson Studio

- If you created a **Watson Studio** service instance in a prior lab, you can relaunch Watson Studio by visiting [http://dataplatform.cloud.ibm.com](http://dataplatform.cloud.ibm.com/)
- Skip the next **Create a Watson Studio service instance** section if you do not need to create a new Watson Studio instance. (Only one Watson Studio instance is allowed per IBM Cloud Lite account).  Jump to the **Watson Studio Projects** section.
- If you want to learn how to navigate the [IBM Cloud Dashboard](https://cloud.ibm.com), click on [Services](https://cloud.ibm.com/resources), then search for *studio* in the masthead.
<div style="page-break-after: always;"></div>
  - **Tip:** Here's a shortcut to locate [your Watson Studio instance](https://cloud.ibm.com/resources?search=studio)
  ![Existing Watson Studio resource screenshot](../screenshots/WatsonStudio-DashboardResource.png)
  - Click on the Watson Studio instance to open and launch Watson Studio.

#### Create a Watson Studio service instance
- Create a **Watson Studio** service instance from the [IBM Cloud Catalog](https://cloud.ibm.com/catalog/?search=studio)
- Search on **Studio** in the IBM Cloud Catalog

![Watson Studio Catalog screenshot](../screenshots/WatsonStudio-Catalog.png)

<div style="page-break-after: always;"></div>
- Click on the **Watson Studio** service tile

![Watson Studio Service screenshot](../screenshots/WatsonStudio-Service.png)

- Click on the **Create** button
- After the Watson Studio service is created, click on **Get Started** or visit Watson Studio at <https://dataplatform.cloud.ibm.com/>

![Watson Studio Launch screenshot](../screenshots/WatsonStudio-Launch.png)

- Login with your IBM Cloud account
- Walk through the introductory tutorial to learn about Watson Studio

<div style="page-break-after: always;"></div>
### Watson Studio Projects

Projects are your workspace to organize your resources, such as assets like data, collaborators, and analytic tools like notebooks and models

#### Create a New Project

- Click on **Create a Project**

![Watson Studio Welcome screenshot](../screenshots/WatsonStudio-Welcome.png)

<div style="page-break-after: always;"></div>
- Select the **Visual Recognition** tile and press the **Create Project** button

![Watson Studio New project screenshot](../screenshots/WatsonStudio-CreateNewProject.png)

- Select a region for Visual Recognition

![Watson Studio Select Region screenshot](../screenshots/WatsonStudio-NewProject-SelectRegion.png)

- Watson Studio will spin for a few seconds while **Preparing Watson Studio** project.  New instances of Watson Visual Recognition and Cloud Object Storage will be created.

![Watson Studio Select Region screenshot](../screenshots/WatsonStudio-PrepareProject-COS.png)

- Give your Project a name : **Flooding**
- The new Cloud Object Storage instance will be prefilled.
- The new Watson Visual Recognition service instance will be prefilled.

- Press the **Create** button

![Watson Studio New project screenshot](screenshots/WatsonStudio-NewProject.png)

You are ready to set up your Project with Watson Visual Recognition. Proceed to the next [step](VISRECO.md)

***

## Chapter Objectives

In this chapter you will create a Visual Recognition model in a Watson Studio Project.  You will learn:

- How to work within a new Watson Studio Project
- How to create a Visual Recognition model

### Watson Studio Projects

Projects are your workspace to organize your resources, such as assets like data, collaborators, and analytic tools like notebooks and models.

#### Rename Visual Recognition Model
- The **Default Custom Model** name is not descriptive so let's rename it
- Click on the **pencil** icon to edit the name

![Watson Studio  screenshot](screenshots/WatsonStudio-VisualRecognitionModelRename1.png)

<div style="page-break-after: always;"></div>
- Rename the model to **Flooding**

![Watson Studio  screenshot](screenshots/WatsonStudio-VisualRecognitionModelRename2.png)

#### Add Custom Classes to the Watson Visual Recognition Model
- Click on the **+** symbol to add a class

![Watson Studio  screenshot](screenshots/WatsonStudio-VisualRecognitionModelAddClass1.png)

<div style="page-break-after: always;"></div>
- Name this class **Flooded Neighborhood**
- Click the **Create** button

![Watson Studio  screenshot](screenshots/WatsonStudio-VisualRecognitionModelFloodedNeighborhoodClass1.png)

- Add a second custom class by clicking on the **+** symbol again

![Watson Studio  screenshot](screenshots/WatsonStudio-VisualRecognitionModelAddClass2.png)

<div style="page-break-after: always;"></div>
- Name this class **Rooftop Survivors**
- Click the **Create** button

![Watson Studio  screenshot](screenshots/WatsonStudio-VisualRecognitionModelRooftopSurvivorsClass2.png)

- Add a third custom class by clicking on the **+** symbol again

- Name this class **Rescue boat**
- Click the **Create** button

![Watson Studio  screenshot](screenshots/WatsonStudio-VisualRecognitionModelRescueBoatClass3.png)

#### Upload Zip Files to Watson Studio Project
- Four zip files have been prepared which contain aerial drone images
- If you following these steps on the web, download the aerial drone zip files here:
  - [flooded-neighborhood.zip](classes/flooded-neighborhood.zip)
  - [rescueboats.zip](rescueboats.zip)
  - [rooftop-survivors.zip](rooftop-survivors.zip)
  - [suburban-neighborhood.zip](suburban-neighborhood.zip)  
- Click on the **Browse** button
- An operating system native File Dialog will open
- Multi-select the four zip files **flooded-neighborhood.zip**, **rescueboats.zip**, **rooftop-survivors.zip**, **suburban-neighborhood.zip**
- Upload these zip files to your Watson Studio project

![Watson Studio  screenshot](screenshots/WatsonStudio-VisualRecognitionModelAddZipFiles.png)

![Watson Studio  screenshot](screenshots/WatsonStudio-VisualRecognitionModelZipFiles.png)

#### Drag the zip files to Custom Classes
- Grab the **rooftop-survivors.zip** from the right navigation and drag it to the **Rooftop Survivors** class

![Watson Studio  screenshot](screenshots/WatsonStudio-VisualRecognitionModelZipFileDrag.png)

- The images in the zip file will be added to the **Rooftop Survivors** class

![Watson Studio  screenshot](screenshots/WatsonStudio-VisualRecognitionModelZipFile2SurvivorsClass.png)

- Grab the **flooded-neighborhood.zip** from the right navigation and drag it to the **Flooded Neighborhood** class

![Watson Studio  screenshot](screenshots/WatsonStudio-VisualRecognitionModelZipFile2FloodedClass.png)

<div style="page-break-after: always;"></div>
- Grab the **rescueboats.zip** from the right navigation and drag it to the **Rescue Boat** class

![Watson Studio  screenshot](screenshots/WatsonStudio-VisualRecognitionModelZipFile2RescueBoatClass.png)

- Grab the **suburban-Neighborhood.zip** from the right navigation and drag it to the **Negative** class

![Watson Studio  screenshot](screenshots/WatsonStudio-VisualRecognitionModelZipFile2NegativeClass.png)

<div style="page-break-after: always;"></div>
#### Train your Watson Visual Recognition Custom Classifier
- Click on the **Train Model** button
- Wait a few (5-10) minutes for the model to train on the images
  ![Watson Studio  screenshot](screenshots/WatsonStudio-VisualRecognitionModelTrain.png)

#### Congratulations
- Once the model has been trained, click on the **Click here** link or the **Trained** link to view and test your model.
  ![Watson Studio  screenshot](screenshots/WatsonStudio-VisualRecognitionModelTrained.png)

<div style="page-break-after: always;"></div>
#### Review and Test
- Review the Classes and Model details
- Click on the **Test** tab

![Watson Studio  screenshot](screenshots/WatsonStudio-VisualRecognitionModelSummary.png)

Test your model in the next [step](VRMTEST.md)

***
<div style="page-break-after: always;"></div>
## Chapter Objectives

In this chapter you will use sample images to confirm your Visual Recognition model. You will learn:

- How to test your Visual Recognition model using sample images
- How to incorporate your Visual Recognition Custom Classifier model into your applications

#### Review and Test
- Review the Classes and Model details
- Click on the **Test** tab
  ![Watson Studio  screenshot](screenshots/WatsonStudio-VisualRecognitionModelSummary.png)

<div style="page-break-after: always;"></div>

### Test Watson Visual Recognition Custom Classifier with sample images
- Visit the [Test Data directory](testdata) and **download** the testdata.zip file.
- Unzip the images and inspect a few of the drone images of flood zones.
- These images were not part of the training set and will be used to validate the visual recognition model.
- Upload the images into the **Test** page by browsing / dragging the images into the Test page

![Watson Studio  screenshot](screenshots/WatsonStudio-VisualRecognitionModelTestBlank.png)

<div style="page-break-after: always;"></div>
- Inspect the scores returned by the Watson Visual Recognition Custom Classifier

![Watson Studio  screenshot](screenshots/WatsonStudio-VisualRecognitionModelTestResults.png)

<div style="page-break-after: always;"></div>
### Implement Watson Visual Recognition custom model in your Applications
- You can incorporate this Watson Visual Recognition Custom Classifier model into your applications using a variety of programming languages - Java, Node, Python, Ruby, Core ML
- Click on the **Implementation** tab to review the Code snippets

![Watson Studio  screenshot](screenshots/WatsonStudio-VisualRecognitionModelImplement.png)

Use the code snippets below to classify images against your model. For reference, the full API specification is available [here](https://www.ibm.com/watson/developercloud/visual-recognition/api/v3/)

- **API endpoint**

  ```
  https://gateway.watsonplatform.net/visual-recognition/api
  ```

- **Authentication**

  ```
  curl -u "apikey:{apikey}" "https://gateway.watsonplatform.net/visual-recognition/api/{method}"
  ```

<div style="page-break-after: always;"></div>
- **Classify an image (GET)**

  ```
  curl -u "apikey:{apikey}" "https://gateway.watsonplatform.net/visual-recognition/api/v3/classify?url=https://watson-developer-cloud.github.io/doc-tutorial-downloads/visual-recognition/fruitbowl.jpg&version=2018-03-19&classifier_ids=Flooding_418020421"
  ```

- **Classify an image (POST)**

  ```
  curl -X POST -u "apikey:{apikey}"-F "images_file=@fruitbowl.jpg" -F "threshold=0.6" -F "classifier_ids=Flooding_418020421" "https://gateway.watsonplatform.net/visual-recognition/api/v3/classify?version=2018-03-19"
  ```

### Congratulations
  You have completed the Drone Visual Recognition Lab and have surveyed flood damaged neighborhoods, identified homes with survivors on rooftops and detected rescue boats.


### Visual Recognition - Additional References
- [Call for Code Visual Recognition](https://developer.ibm.com/callforcode/resources/visual-recognition/)
- [Identify Cities from Space](https://developer.ibm.com/code/patterns/identify-cities-from-space/)
- [Locate and count items with object detection](https://developer.ibm.com/code/patterns/locate-and-count-items-with-object-detection/)
- [Classify vehicle damage images](https://developer.ibm.com/code/patterns/classify-vehicle-damage-images/)
