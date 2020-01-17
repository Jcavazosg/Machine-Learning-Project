Installing The Tensorflow Object Detection Api

-Cloned Tensorflow/models  repository
-Created environment in anaconda prompt - activate Tensorflow_cpu

-installed dependencies:
•	pip install --user Cython
•	pip install --user contextlib2
•	pip install --user pillow
•	pip install --user lxml
•	pip install --user jupyter
•	pip install --user matplotlib
•	pip install --user opencv-python

 
COCO API installation
-install pycocotools
-pip install git+https://github.com/philferriere/cocoapi.git#subdirectory=PythonAPI
-Visual C++ 2015 build tools must be installed and on your path

Protobuf Installation 

The Tensorflow Object Detection API uses Protobufs to configure model and training parameters. So Protobuf libraries have to be downloaded and compiled first. 

**I followed the Gilbert Tanner tuturial on this part as a script was written that worked flawlessly and i did not have to mess 	with program files folders and path environments .
https://github.com/protocolbuffers/protobuf/releases

-downloaded: protoc-3.11.2-win64.zip [use_protobuf1.py script written for installation and located in models/research folder) 
	- mac os ones if needed: [protoc-3.11.2-osx-x86_32.zip] or [protoc-3.11.2-osx-x86_64.zip]
- Tensorflow Object Detection API uses .proto files.
- The files need to be compiled into .py files in order for the Object Detection API to work properly. 
- Google provides a program called Protobuf that can compile these files.


Adding Environment Variables
option 1: Add folder-TensorFlow_cpu/models/research/object_detection to your {PYTHONPATH}
option 2: In folder-Tensorflow_cpu/models/research, run following:
•	python setup.py build
•	python setup.py install

[setup.py file] for object detection 
located in:  TensorFlow_cpu/models/research/


***The default metrics are based on those used in Pascal VOC evaluation. To use the COCO object detection metrics add metrics_set: “coco_detection_metrics” to the eval_config message in the config file. To use the COCO instance segmentation metrics add metrics_set: “coco_mask_metrics” to the eval_config message in the config file.

Create Label Map

- TensorFlow requires a label map, which namely maps each of the used labels to an integer values. This label map is used both by the training and detection processes.
-label map files use the .pbtxt extention

Creating TensorFlow Records

After generating annotations and splitting dataset into training and testing subsets, need to convert  annotations(images / xml files) into the  TFRecord format by following:
•	Converting the individual *.xml files to a unified *.csv file for each dataset [train & test]
•	Converting the *.csv files of each dataset to *.record files (TFRecord format) [train & test]

**scripts for process described above:
	[xml_to_csv.py]
	[generate_tfrecords.py]






