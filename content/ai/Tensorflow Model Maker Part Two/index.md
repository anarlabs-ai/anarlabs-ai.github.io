---

title: "Deploying Object Detection App into Android & EDGE Devices Part Two "
description: "In this post, we will demonstrate how to deploy the object detection model that we built in the previous post to both Android and edge devices. The model was built using the TensorFlow Model Maker API and the efficientdet-lite model, which is optimized for mobile and edge devices"  
keywords: 
    - AI 
    - Machine Learning
    - Data
    - AutoML
draft: false 
author: "Abdullah Al Hadrami"
showToc: true
TocOpen: false
draft: false
hidemeta: false
comments: false
showReadingTime: true
ShowReadingTime: true
ShowBreadCrumbs: true
ShowPostNavLinks: true
ShowWordCount: true
UseHugoToc: true
---

You can refer to the previous post to learn how to build the object detection model using the TensorFlow Model Maker API and the efficientdet-lite model
(https://www.aivision.app/ai/tensorflow-model-maker-part-two/)

## Live Demo for Android and EDGE Device 

Here is the live demo for Object Detection App on Android and Edge Devices.



 {{< youtube tkFKGSHs1Ks >}}

## Clone the Repo 

```bash

git clone https://github.com/Abdullamhd/od_efficientdet
    
```

## Building the Object Detection App for Android

### Prerequisites
- Android Studio
- Android Device with Android 8 or higher.


Once you have cloned the repo, you can open the project in Android Studio. The project is located in the 
`android_od` folder.

### Running the App
once you open the project, Wait for the gradle to build the project and then you can run the app on your Android device, make sure the usb debugging is enabled on your device and you have connected it to your computer.


### Building the App with your own model
if you built your own model and want to use it in the app, you can replace the model file located in 
`android_od/app/src/main/assets` with your own model file.
then replace the model name in the file `ObjectDetectorHelper.kt` in the method `setupObjectDetector()` with your model name , line 85 , 
if you built only on model just assign the model name to the variable `modelName` like this:

```kotlin

        val modelName = "YourModel.tflite"

```
if you built multiple models, you can use the `when` statement to assign the model name to the variable `modelName` like this , assuming you built 5 models

```kotlin

        val modelName =
            when (currentModel) {
                MODEL_EFFICIENTDETV0 -> "Apple_Orange_arch0.tflite"
                MODEL_EFFICIENTDETV1 -> "Apple_Orange_arch1.tflite"
                MODEL_EFFICIENTDETV2 -> "Apple_Orange_arch2.tflite"
                MODEL_EFFICIENTDETV3 -> "Apple_Orange_arch3.tflite"
                else -> "Apple_Orange_arch4.tflite"
            }

```

make sure to replace the model names with your own model names.
then you can build and run the app on your Android device.







## Building the Object Detection App for Edge Devices

### Prerequisites
- PC or Raspberry Pi or EDGE Device with Linux OS
- OS : Windows WSL2 or Linux OS(Debian, Ubuntu, etc..)
- Python 3.7 or higher

### Running the App

assuming you have IP camera or webcam connected to your computer,  if you don't have one, you can use the IP camera simulator app on your phone named "IP Webcam" , search for it on the play store and install it, then run the app , from the app go to menu and select "Start Server", the app will display the IP address and port number,you can use it to connect to the camera from your computer.
then open file `detect.py` and replace the IP address and port number with your own , on line 22 , 23




```python
IP = '192.168.0.102' # TODO change this to your camera's IP address
PORT = '8080' # TODO change this to your camera's port number
URL = 'h264_ulaw.sdp'
ip_camera_url = 'rtsp://' + IP + ':' + PORT + '/' + URL
```
then run the following command to install the required packages , make sure you are in the `edge_od` folder
    
```bash
    pip install -r requirements.txt
```
    
then run the following command to run the app
    
```bash
    python detect.py
```

The dialog box will open with live video feed from the camera , then you can point to the objects you want to detect , in our case we are detecting apples and oranges , the app will display the detected objects with the confidence score with bounding boxes around them , you can also press the `q` key to quit the app.

### Building the App with your own model
if you built your own model and want to use it in the app, you can replace the model file located in
`edge_od` with your own model file.
then replace the model name in the file `detect.py` line 25 with your model name , because i built 5 models, i created a dictionary to store the model names and their corresponding index, in your case you can just assign the model name to the variable `selected_model` like this:

`

```python
MODEL_PATHS = {
  0 : 'Apple_Orange_arch0.tflite',
  1 : 'Apple_Orange_arch1.tflite',
  2 : 'Apple_Orange_arch2.tflite',
  3 : 'Apple_Orange_arch3.tflite',
  4 : 'Apple_Orange_arch4.tflite',
}

selected_model = MODEL_PATHS[0] # TODO change MODEL_PATHS[0] to your model name
```

then you can run the app with your own model.

## Conclusion

I hope you enjoyed this post, if you have any questions or suggestions, please reach out to me on twitter @Alhadrami 

















