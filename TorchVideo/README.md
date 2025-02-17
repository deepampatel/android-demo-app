# PyTorch Video Classification on Android

## Introduction

The newly released open-sourced [PyTorchVideo](https://github.com/facebookresearch/pytorchvideo) adds video understanding to the rapidly growing PyTorch ecosystem. This PyTorchVideo Classification on iOS demo app shows how to use a pre-trained PyTorchVideo classification model on iOS to see video classification results, updated per second while the video plays, on tested videos, videos from the Photos library, or even real-time videos.

## Prerequisites

* PyTorch 1.8.0/1.8.1, torchvision 0.9.1, PyTorchVideo (Optional)
* Python 3.8 or above (Optional)
* Android Pytorch library 1.8.0, torchvision library 1.8.0
* Android Studio 4.0.1 or later

## Quick Start

### 1. Prepare the Model (Optional)

If you don't have the PyTorch environment set up to run the script, you can download the model file `video_classification.pt` [here](https://drive.google.com/file/d/1qweDu7QZv7xJA7Sx_UIxjvcS7y1rQ2kE/view) to the `android-demo-app/TorchVideo/app/src/main/assets` folder, then skip the rest of this step and go to step 2 directly.

Be aware that the downloadable model file was created with PyTorch 1.8.0, matching the PyTorch Android library 1.8.0 specified in the project's `build.gradle` file as `implementation 'org.pytorch:pytorch_android:1.8.0'`. If you use a different version of PyTorch to create your model by following the instructions below, make sure you specify the same PyTorch Android library version in the `build.gradle` file to avoid possible errors caused by the version mismatch. Furthermore, if you want to use the latest PyTorch master code to create the model, follow the steps at [Building PyTorch Android from Source](https://pytorch.org/mobile/android/#building-pytorch-android-from-source) and [Using the PyTorch Android Libraries Built](https://pytorch.org/mobile/android/#using-the-pytorch-android-libraries-built-from-source-or-nightly) on how to use the model in Android.

To create the model yourself, simply run the following commands:
```
conda create -n pt181 python=3.8.5
conda activate pt181
pip install torch torchvision

# pip list|grep torch
# torch             1.8.1
# torchvision       0.9.1

pip install pytorchvideo

cd android-demo-app/TorchVideo
python build_model.py

```
The model file `video_classification.pt` will be created and saved in the `app/src/main/assets` folder.

### 2. Build with Android Studio

Start Android Studio, then open the project located in `android-demo-app/TorchVideo`

### 3. Run the app

Select an Android emulator or, to test videos from your Camera Roll or live video, select an Android device to run the app. You can go through the included pre-recorded test videos to see the classification results per second. You can also select a video from your Android device's Camera Roll, or use camera to do live video classification - see this [video](https://drive.google.com/file/d/193tkZgt5Rlk7u-EQPcvkoFtmOQ14-zCC/view) for a screencast of the app running.

Some screenshots of the video classification results are as follows:

![](screenshot1.png)
![](screenshot2.png)
![](screenshot3.png)
