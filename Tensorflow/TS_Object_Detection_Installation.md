Installing The Tensorflow Object Detection Api

Cloned the  Tensorflow/models repository
Created Tensorflow environment - cpu 
-installed required dependencies:
	pip install --user Cython
	pip install --user contextlib2
	pip install --user pillow
	pip install --user lxml
	pip install --user jupyter
	pip install --user matplotlib
	pip install --user opencv-python
	 
#COCO API installation
- COCO is a large image dataset designed for object detection, segmentation, person keypoints detection, stuff segmentation, and caption generation. 
-install pycocotools
-pip install git+https://github.com/philferriere/cocoapi.git#subdirectory=PythonAPI
-Visual C++ 2015 build tools must be installed and on your path

#Protobuf Installation 

The Tensorflow Object Detection API uses Protobufs to configure model and training parameters. So Protobuf libraries have to be downloaded and compiled first. 

https://github.com/TannerGilbert/Tensorflow-Object-Detection-API-Train-Model
**I followed the Gilbert Tanner tuturial on this part as a python script was provided that executes the command for each .proto file. The Tensorflow command provided did not work on my sysem. 

-downloaded: protoc-3.11.2-win64.zip [use_protobuf1.py script written for installation and located in models/research folder) 
	- mac os ones if needed: [protoc-3.11.2-osx-x86_32.zip] or [protoc-3.11.2-osx-x86_64.zip]
- Tensorflow Object Detection API uses .proto files.
- The files need to be compiled into .py files in order for the Object Detection API to work properly. 
- Google provides a program called Protobuf that can compile these files.

#Adding Environment Variables
option 1: Add folder-TensorFlow_cpu/models/research/object_detection to your {PYTHONPATH}
option 2: In folder-Tensorflow_cpu/models/research, run following:
	python setup.py build
	python setup.py install
**with option 2, anytime you exit out of the anaconda prompt, you must run the two python scripts again or you will have errors

[setup.py file] for object detection 

#Create Label Map

- TensorFlow requires a label map, which  maps each of the used labels to an integer values. This label map is used both by the training and detection processes.
-label map files use the .pbtxt extention

#Creating TensorFlow Records

After generating annotations and splitting dataset into training and testing subsets, we converted the images and xml files into the  TFRecord format by following:
	Converting the individual *.xml files to a unified *.csv file for each dataset [train & test]
	Converting the *.csv files of each dataset to *.record files (TFRecord format) [train & test]








