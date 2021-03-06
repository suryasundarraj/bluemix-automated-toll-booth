# Smmart Toll Booth with IBM Bluemix and Mediatek LinkItONE

This is the project repository for Smart Highway Toll Collection System. Refer to the sections below for configuration , build and deployment instructions. 

This is the accompanying project for this blog post.

# Components

The project has following components

## Hardare setup for toll booth
Refer the hardware setup and schematic in the blog post.

The BOM for Hardware components is 

1. Mediatek Linkit ONE Board (1 no.)

2. RFID reader Module - EM 18  (1 no.)

3. Servo Motor - V3006 (1 no.)

## Backend Server Setup

The backend server for this project is hosted on IBM Bluemix. PubNub is also used for messaging purposes between the server and hardware and app. You will need to sign up for Bluemix and PubNub subscription.

## Mobile App
User mobile app for managing individual toll transactions. The app is based on Apache Cordova 


#Device Build

Follow these instructions to build the toll booth device sofwware for LinkitONE. 

Prerequisites : You will have to be familiar with Arduino IDE and have it installed on your laptop/PC.

Step 1: Setting up the Arduino IDE to Program the Linkit ONE

Installing the Arduino Linkit ONE Core with the Boards Manager

Download and Install Arduino 1.6.6 from [https://www.arduino.cc/en/Main/Software]
Start Arduino and open Preferences window.
Enter http://download.labs.mediatek.com/package_mtk_linkit_index.json into Additional Board Manager URLs field.
You can add multiple URLs, separating them with commas.
Open Boards Manager from Tools > Boards > Board menu and install.

#Uploading the Program to the LINKIT ONE using the Arduino IDE

Step 1: Get this Git Repo to your desktop using,

https://github.com/suryasundarraj/bluemix-automated-toll-booth.git

Step 2: Open the codes in Arduino IDE

Step 3: Select Linkit One from the Device List

Step 4: Select the USB Port from Tools - > Linkit Debug Port

Step 5: Edit the SSID and PASSWORD to configure to your router

Step 6: Edit the pubnub publish and subscribe keys to your unique key provided by pubnub.com(if required)

Step 7: Upload the Code to the Linkit ONE

#MOBILE APP BUILD

Steps to be followed to Build and Run the Android App for Automated System (Note : Assumed Cordova framework installed in your system) (For pre-compiled app follow Step 4) Step 1 : Change the cordova project directory

    cd (folder_name)
Step 2 : Modify the pubnub publish and subscribe keys at www/js/index.js

Step 3 : Build the .apk file using,

    cordova build android
Step 4 : Once the .apk file is build successfully, you will find the app at this path

    ./platforms/android/build/output/android-debug.apk
Step 5 : Install the APP on an Android Phone.
