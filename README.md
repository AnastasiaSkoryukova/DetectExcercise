# Nano Challenge X (Daiquiri) - Machine Learning


# Objective
The objective of this project is to use Apple provided machine learning tools such as CreateML, to train a simple model that can accurately detect specific, simple body movements (actions). The types of body actions that will be trained are:

* Reach
* Squats
* Random (random body movements)


# Process
The high level steps and process to train a model are as follows:


## Data Creation (videos)
* Using an iphone, record a series of videos to capture the motion of each body action
* Each video should only record the action of the intended body movement
* Record multiple videos of each action (approx. 50 videos per action) so that enough data is available to effectively train the model
* The following image shows the video recording of the sqaut body action

![Video recording of Squat Body Action](/Documentation/detecting-human-squat-action.png)


## Model Training with Create ML Mac App
* After recording enough data (videos) of each body action, split the data of each action into training and test folders, allocating around 20% of the videos to the test folder and the reminaing 80% to the validation folder. For example, if you record 50 videos of a specific body action, place 40 vidoes into the training folder and the reminaing 10 into the testing folder
* The training folder is used by Create ML to train the model, while the test folder is used by Create ML to verify the trained data
* The following image shows Create ML training the model in real time. The graph indictaes the iterations performed and the level of confidence over time, as the data is analyzed to train the model  

![Create ML Model Training Graph](/Documentation/cml-action-classifier.png)


## Trained Model Output
* After some time, depending on the settings used to train the model (such as iterations, video frame rate etc), the model will be ready
* The following is a summary of the meta data produced

![Create ML Trained Model](/Documentation/cml-model.png)


## Create ML Model Verification
* To ensure the model correctly detects the trained body actions, record a video of a random person performing the action
* Then import the video into the Preview Pain of Create ML and run, as shown in the following video

https://user-images.githubusercontent.com/44283704/160300134-27cd70dd-be01-45ff-bfbf-6c084ce746d1.mov


# Vision Framework and iOS Sample App

To apply the knowledge we learnt during the research phase of our learning process, we used the sample app, “Guess my Exercise” provided by Apple at WWDC 2020. 

Using the sample app we replaced the existing model with our own trained model and changed the labels for the actions of our model (squat and reach) so the correct text was displayed for each action.

In addition we added a sound feature to the app to play a sound when the “non-negative” actions, squats and reaches were detected. The sound is played when the level of confidence of the prediction reaches a certain level. 


