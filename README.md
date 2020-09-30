# Emergency-Signal-Recognition-for-the-Hearing-Impaired-using-Multichannel-CNN


<img alt="GitHub issues" src="https://img.shields.io/github/issues/source-aasf/gladiator"> <img alt="GitHub Hacktoberfest combined status" src="https://img.shields.io/github/hacktoberfest/2020/source-aasf/gladiator"> ![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=flat-square) [![Open Source Love](https://badges.frapsoft.com/os/v1/open-source.svg?v=103)](https://github.com/ellerbrock/open-source-badges/)

We live in a world where auditory means are used to warn people of Emergency situations. For the hearing impaired, comprehending such auditory signals becomes impossible. So this system aims to notify the hearing imapired of the emergency situations by identifying emergency signals such as Police sirens, Ambulance siren, Fire alarms. The task is classify the background audio signal as emergency or non-emergency. This model can be deployed in an Android app that vibrates to notify the hearing impaired in the case of an emergency. Further this can be deployed on a smart-watch or a fitness band.

## Dataset

The dataset used was Google's Audioset. A part of Audioset was used for this study, out of the 632 event classes present in Audioset only 35 classes were used. Classes such as Sirens, alarms, buzzers were marked as emergency while sounds of wind, traffic noises, rain, etc. were marked as non-emergency. The file data_aquisition.py consists of the python script for extracting the 10 second audio-clips from the video links in Audioset csv file. To extract the data run that script, and change the target folder to the desired directory. 

## Data Preprocessing 

- Converting raw audio clips to Mel spectrograms by making use of Librosa library.
![alt text](https://github.com/paddy-03/Emergency-Signal-Recognition-for-the-Hearing-Impaired-using-Multichannel-CNN/blob/master/original.png)
- Using traditional audio augmentation techniques such as adding white noise, time stretching, time shifting to increase the size of training data.
- Using Mixup augmentation technique for effectively generating new clips from existing ones.

## Learning Model

A multichannel CNN architecture was implemented, which made use of 4 different channels to extract features from spectrograms, and then the 4 channels are merged using the Add() layer in Keras. 
![alt text](https://github.com/paddy-03/Emergency-Signal-Recognition-for-the-Hearing-Impaired-using-Multichannel-CNN/blob/master/architecture3.png)

## App Deployment

The model was deployed as an android app that sensed and recorded sounds from the environment. In case of any emergency sounds, the phone was made to vibrate.
</br>
![alt text](https://github.com/rshivam08/Emergency-Signal-Recognition-for-the-Hearing-Impaired-using-Multichannel-CNN/blob/master/android_deployment.png)
</br>
You can find the android app code <a href="https://github.com/rshivam08/Deaf-Assistant"> here. </a>

## Requirements

- Python 3
- Numpy 
- Librosa
- Keras
- Matplotlib
- Seaborn
- Sklearn
