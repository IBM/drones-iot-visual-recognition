*Quick links :*
[Home](/README.md) - [Flooding](FLOODING.md) - [Watson Studio](STUDIO.md) - [**Visual Recognition Model**](VISRECO.md) - [Test and Deploy](VRMTEST.md)
***

## Lab Objectives

In this lab you will create a Visual Recognition model in a Watson Studio Project.  You will learn:

- How to work within a new Watson Studio Project
- How to create a Visual Recognition model

### Watson Studio Projects

Projects are your workspace to organize your resources, such as assets like data, collaborators, and analytic tools like notebooks and models.

#### Rename Visual Recognition Model
- The **Default Custom Model** name is not descriptive so let's rename it
- Click on the **pencil** icon to edit the name

![Watson Studio  screenshot](screenshots/WatsonStudio-VisualRecognitionModelRename1.png)

- Rename the model to **Flooding**

![Watson Studio  screenshot](screenshots/WatsonStudio-VisualRecognitionModelRename2.png)

#### Add Custom Classes to the Watson Visual Recognition Model
- Click on the **+** symbol to add a class

![Watson Studio  screenshot](screenshots/WatsonStudio-VisualRecognitionModelAddClass1.png)

- Name this class **Flooded Neighborhood**
- Click the **Create** button

![Watson Studio  screenshot](screenshots/WatsonStudio-VisualRecognitionModelFloodedNeighborhoodClass1.png)

- Add a second custom class by clicking on the **+** symbol again

![Watson Studio  screenshot](screenshots/WatsonStudio-VisualRecognitionModelAddClass2.png)

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

- Grab the **rescueboats.zip** from the right navigation and drag it to the **Rescue Boat** class

![Watson Studio  screenshot](screenshots/WatsonStudio-VisualRecognitionModelZipFile2RescueBoatClass.png)

- Grab the **suburban-Neighborhood.zip** from the right navigation and drag it to the **Negative** class

![Watson Studio  screenshot](screenshots/WatsonStudio-VisualRecognitionModelZipFile2NegativeClass.png)

#### Train your Watson Visual Recognition Custom Classifier
- Click on the **Train Model** button
- Wait a few (5-10) minutes for the model to train on the images

![Watson Studio  screenshot](screenshots/WatsonStudio-VisualRecognitionModelTrain.png)

#### Congratulations
- Once the model has been trained, click on the **Click here** link or the **Trained** link to view and test your model.

![Watson Studio  screenshot](screenshots/WatsonStudio-VisualRecognitionModelTrained.png)

#### Review and Test
- Review the Classes and Model details
- Click on the **Test** tab

![Watson Studio  screenshot](screenshots/WatsonStudio-VisualRecognitionModelSummary.png)

Test your model in the next [step](VRMTEST.md)

*Quick links :*
[Home](README.md) - [Flooding](FLOODING.md) - [Watson Studio](STUDIO.md) - [**Visual Recognition Model**](VISRECO.md) - [Test and Deploy](VRMTEST.md)
