---
title: "DonkeyCar Test4"
date: 2017-11-15T22:12:57-08:00
draft: false
categories:
- donkeycar
tags:
- tensorflow
- autonmous vehicle
- keras
keywords:
- neural network
- tensorflow
- keras
comments: true
showMeta: true
showActions: true
thumbnailImage: /img/donkeycar/test4/loss.png
thumbnailImagePosition: left
gallery: 
- /img/donkeycar/test4/loss.png /img/donkeycar/test4/loss.png "Loss"
- /img/donkeycar/test4/angle_out_loss.png /img/donkeycar/test4/angle_out_loss.png "Angle Out Loss"
- /img/donkeycar/test4/angle_out_acc.png /img/donkeycar/test4/angle_out_acc.png "Angle Out Accuracy"
- /img/donkeycar/test4/throttle_out_loss.png /img/donkeycar/test4/throttle_out_loss.png "Throttle Out Loss"
- /img/donkeycar/test4/throttle_out_acc.png /img/donkeycar/test4/throttle_out_acc.png "Throttle Out Accuracy"
---

Donkeycar Test 4

#### Descriptions
I am testing here the number of epochs to use.  I am monitoring the Loss to make sure it drops and if it plateaus.  If it plateaus, where does it begin to plateau.  I am also using a very small dropout and using RMSPROP.  The learning rate is left default.  

Good results will have the car remaining on the track consitently.  It may drive off, in certain areas if the training is not good, but it should for the most part stay within the lines.  The video shows the result of the parameters.

#### Parameters
* 50 Epochs
    * Typically only need 23 for early stop to end
* RMSPROP
    * Could also use Adam
* 10% Dropout
    * Typically you see 50%
* 1e-4 Learning Rate
    * A default value to start with

#### Results:
{{< alert warning >}}
Pretty good results.  Went off the track in certain areas.
{{< /alert >}}

{{<  youtube REoOGzdBbes >}}


{{< codeblock "config.py" "configPY" "/img/donkeycar/test4/config.py" "config.py" >}}
# TRAINING
BATCH_SIZE = 128
TRAIN_TEST_SPLIT = 0.8

# Keras settings
TRAINING_MODEL = MODEL_TYPE_CATEGORICAL     # Type of Neural Network model
IS_TENSORBOARD = True                       # Create Tensorboard data
IS_PLOT_RESULTS = True                      # Create matplotlib plots
IS_EARLY_STOP = False                       # If no improve, stop training early
EARLY_STOP_COUNT = 5                        # Number of no changes before stopping
LEARNING_RATE = 1.0e-4                      # Learn rate.  Decrease to fix bias
EPOCHS = 50                                 # Number of epochs to run.
DROPOUT_1 = 0.1                             # First Dropout percentage
DROPOUT_2 = 0.1                             # Second Dropout percentage
OPTIMIZER = OPTIMIZER_TYPE_RMSPROP          # Type of Optimizer to use.
LOSS_WEIGHT_ANGLE = 0.9                     # Loss weight for Angles
LOSS_WEIGHT_THROTTLE = 0.001                # Loss Weight for Throttle        {{< /codeblock >}}             


![Test 4 Loss Plot](/img/donkeycar/test4/loss.png)

![Test 4 Angle Out Loss Plot](/img/donkeycar/test4/angle_out_loss.png)

![Test 4 Angle Out Accuracy Plot](/img/donkeycar/test4/angle_out_acc.png)

![Test 4 Throttle Out Loss Plot](/img/donkeycar/test4/throttle_out_loss.png)

![Test 4 Throttle Out Accuracy Plot](/img/donkeycar/test4/throttle_out_acc.png)


#### Gallery
  
   
  