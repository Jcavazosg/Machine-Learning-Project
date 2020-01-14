Directory Tree Structure

TensorFlow_cpu
│
│
├─ bin (protoc.exe)
│
├─ include (protoc-3.11.2-win64 download/google/ protobuf file for windows)
│
├─ LabelImg_tool
│   └─ windows_v1.8.0_labelexe
│
├─ models
│   ├─ official
│   ├─ research
│   ├─ samples
│   └─ tutorials
│
├─ scripts [xml_to_csv.py / generate_tfrecord.py]
│
└─ preprocessing [train & test csv's/train & test tf records]
│
│
└─ workspace
    │ 
    └─ training_demo **(legacy_train.py file)
            |
            |____annotations [coco_label_map.pbtxt/test_labels.csv/train_labels.csv/record/test.record]
            |
            |____images   (jpg images & xml files)
            |             |
            |             └─ test
            |             └─train                        
            |
            |____pre-trained-model [ssd_inception_v2_coco.config + 										ssd_inception_v2_coco tar.gz]
            |
            |____training [train.py script]
