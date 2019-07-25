*Quick links :*
[Home](/README.md) - [WildFires](WILDFIRES.md) - [Watson Studio](STUDIO.md) - [Visual Recognition Model](VISRECO.md) - [**Test and Deploy**](VRMTEST.md)
***

## Lab Objectives

In this lab you will use sample images to confirm your Visual Recognition model. You will learn:

- How to test your Visual Recognition model using sample images
- How to incorporate your Visual Recognition Custom Classifier model into your applications

#### Review and Test
- Review the Classes and Model details
- Click on the **Test** tab

![Watson Studio  screenshot](screenshots/WatsonStudio-VisualRecognitionModelSummary.png)

### Test Watson Visual Recognition Custom Classifier with sample images
- Visit this [UK Daily Mail article](http://www.dailymail.co.uk/news/article-6045685/Incredible-drone-images-charred-trees-burnt-homes-eighth-person-dies-California.html) and **download** a few of these drone images of devastated California neighborhoods
- These images were not part of the training set and will be used to validate the visual recognition model
- Return to the **Test** tab in the Watson Studio Flooding project
- There are two techniques to upload the images into the **Test** page
  - Drag the individual images from your local file browser into the Test page
  - Click on the **browse** link to open a file selection dialog

![Watson Studio  screenshot](screenshots/WatsonStudio-VisualRecognitionModelTestBlank.png)

- The trained custom classifier model will analyze the images
- Inspect the **Confidence scores** returned by the Watson Visual Recognition Custom Classifier

![Watson Studio  screenshot](screenshots/WatsonStudio-VisualRecognitionModelTestImage.png)

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

- **Classify an image (GET)**

  ```
  curl -u "apikey:{apikey}" "https://gateway.watsonplatform.net/visual-recognition/api/v3/classify?url=https://watson-developer-cloud.github.io/doc-tutorial-downloads/visual-recognition/fruitbowl.jpg&version=2018-03-19&classifier_ids=CountBurnedHomes_1382538940"
  ```

- **Classify an image (POST)**

  ```
  curl -X POST -u "apikey:{apikey}"-F "images_file=@fruitbowl.jpg" -F "threshold=0.6" -F "classifier_ids=CountBurnedHomes_1382538940" "https://gateway.watsonplatform.net/visual-recognition/api/v3/classify?version=2018-03-19"
  ```

### Congratulations
  You have completed the Drone Visual Recognition Lab and have surveyed wildfire damaged neighborhoods and identified burned homes and intact homes.


### Visual Recognition - Additional References
- [Call for Code Visual Recognition](https://developer.ibm.com/callforcode/resources/visual-recognition/)
- [Identify Cities from Space](https://developer.ibm.com/code/patterns/identify-cities-from-space/)
- [Locate and count items with object detection](https://developer.ibm.com/code/patterns/locate-and-count-items-with-object-detection/)
- [Classify vehicle damage images](https://developer.ibm.com/code/patterns/classify-vehicle-damage-images/)

*Quick links :*
[Home](/README.md) - [WildFires](WILDFIRES.md) - [Watson Studio](STUDIO.md) - [Visual Recognition Model](VISRECO.md) - [**Test and Deploy**](VRMTEST.md)
