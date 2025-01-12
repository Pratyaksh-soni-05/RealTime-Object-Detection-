# RealTime-Object-Detection-

TensorFlow Object Detection API - Model Training Pipeline

This project involves setting up and training an object detection model using the TensorFlow Object Detection API. The goal is to create a custom object detection pipeline to identify and classify specific objects in images by leveraging TensorFlow's pretrained models.

Features:
-Custom Dataset Support: Train the model with a labeled dataset of your choice.
-Model Training: Fine-tune a pre-trained SSD MobileNet model for custom object detection.
-Data Pipeline: Generate TFRecord files for training and testing.
-Configurable Pipeline: Modify and manage pipeline.config for model customization.

Tensorflow/
├── workspace/
│   ├── annotations/      # Annotation files (label_map.pbtxt, TFRecords)
│   ├── images/           # Training and testing images
│   ├── models/           # Custom models and pipeline.config
│   └── pre-trained-models/  # Pre-trained TensorFlow models
├── scripts/
│   └── generate_tfrecord.py  # Script to generate TFRecords
├── models/               # TensorFlow models repository (cloned)

Steps to Build the Pipeline
1) Clone TensorFlow Models Repository: Clone the TensorFlow Object Detection API repository:
git clone https://github.com/tensorflow/models Tensorflow/models

Generate TFRecord Files: Use the generate_tfrecord.py script to convert labeled images into TFRecord format:
python Tensorflow/scripts/generate_tfrecord.py -x Tensorflow/workspace/images/train -l Tensorflow/workspace/annotations/label_map.pbtxt -o Tensorflow/workspace/annotations/train.record
python Tensorflow/scripts/generate_tfrecord.py -x Tensorflow/workspace/images/test -l Tensorflow/workspace/annotations/label_map.pbtxt -o Tensorflow/workspace/annotations/test.record

Configure the Model Pipeline: Update the pipeline.config file located in Tensorflow/workspace/models/my_ssd_mobnet/. Adjust settings such as:

Number of classes.
Batch size.
TFRecord file paths.
Train the Model: Start training the model using the TensorFlow Object Detection API.


