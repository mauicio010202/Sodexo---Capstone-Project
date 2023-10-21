This repository was made for the RPI capstone project class May 2023 "Automation of Commons Dining Hall Dish Room". The following files were used to train and demosntrate a neural network.

The model chosen was made to differentiate compostable waste from non-compostable waste. The model was trained using tensorflow, and the computer vision elements were applied using OpenCV. All of the code is generated in python, but the files are in Jupyter format as it was convenient for working with large data.

The model was trained using the fine-tuning documentation and tutorial from the tensorflow webpage: https://www.tensorflow.org/tutorials/images/transfer_learning. The model was trained using the following dataset publicly available at Kaggle: https://www.kaggle.com/datasets/rayhanzamzamy/non-and-biodegradable-waste-dataset. For this instance of the project, the model was trained uniquely using the first training set of this dataset. 

The saved_model folder holds all the files of the saved model. The "common_photos" directory hold images taken to test for some of the non-compostable items encounterable at commons dinning hall. The "efficientdet_lite2_detection_1" directory holds an object detection model used for demonstration combined with openCV.

In this repository, the directory containing the dataset from kaggle is missing due to memory consumption. The local repository had the dataset locally named as "dataset" as it may appear on some of the code included. 

The jupyter files used are detailed as follows:

-photos.ipynb: this file includes the code that was used to train the NN using the kaggle dataset 

-camera.ipynb: this file includes a demonstration of the object recognition working with the trained model. The code works by letting the object detection identify the cooridinates of an objected, transformind those coordinates into a square, reshaping it to fit the trained model, and using that prediction to determine whether it is compostable or non-compostable. Not very accurate so far, could use some improvement. 

-frame_nn_camera.ipynb: this file includes a demonstration of the trained model working without any object detection. It just takes the frame from the camera and makes the trained model analyze whether the contents of it are overall compostable or non-compostable

-snapshot.ipynb: this file takes a local image and goes through the same process as "camera.ipynb" but for that single image

-object_Detection_local.ipynb: creates a hardcoded rectangle frame on an image to demonstrate how the object detection allows to take a fraction of the frame focusing in a single object at the time

-local_img_NN.ipynb: it gives a prediction from a local image using the trained model  