# Dataset file structure
---------------------------
Images
     -----test
     -----train
     
# Real_Time_Object_Detection commands

# xml_to_csv.py
----------------------------------
python xml_to_csv.py

# generate_tfrecord.py
----------------------------------------
python generate_tfrecord.py --csv_input=Images/train_labels.csv --image_dir=Images/train --output_path=Images/train.record
python generate_tfrecord.py --csv_input=Images/test_labels.csv --image_dir=Images/test --output_path=Images/test.record

# set python path
----------------------------------------------
set PYTHONPATH=path_to_slim_directory_in_tensorflow

# train.py
-----------------------------------------------------
python train.py --logtostderr --train_dir=training_dir/ --pipeline_config_path=Images_training/faster_rcnn_inception_v2_coco.config

# add this step in config file to stop it running infinitely
---------------------------------------------------------------
num_steps: 200000

# export_inference_graph.py
--------------------------------
python export_inference_graph.py --input_type image_tensor --pipeline_config_path path_to_downloaded_model --trained_checkpoint_prefix path_to_trained_model --output_directory model_inferencegraph_output

# testing the images
------------------------------
Create TEST folder and paste images in the folder and then run the jupyter notebook  
