# Specialization Project
This github repository is created as a supplementary resource to my specialization project conducted during the fall of 2019. The focus of the project was to fine-tune a Faster R-CNN object detection model using the Tensorflow API in order to detect and localize cores within optical core images used in the petroleum industry. This repository presents the results generated by the three models (benchmark, M1, M2) outlined in the project report. Additonally, the weights from the three models and inference graph from the final model (M2) is made available so that they can be trained further, or be used directly for inference. 


![Alt Text](https://github.com/Adelved/specialization-project/blob/master/logo.jpg)

## Appendix
The [Appendix](Appendix) directory contains the files and scripts mentioned in Methodology chapter of the report ([files](Appendix/scripts)), the [configuration files](Appendix/configuration_files) for the three models, as well as the [data](Appendix/data) used. The original images are provided in .jpeg format and the labeld data is provided in the formats: .xml, .csv and .tfrecord. Additionally, the predictions on the validation set for the three models and the M2 predictions on test set is presented in [predictions_results](Appendix/predictions_results). Notice that some of the images with the predicted bounding boxes are too large to be previewed on github, and must be downloaded in order to be viewed.
The files in the Appendix directory are mainly intented for viewing and not for further use. Thus, the file paths in the configuration files are specific for project structure of the author. 
## Further Training and Inference
This section requires the user to install Tensorflow and setup the Tensorflow Object Detection Environment, which can be done by following the [installation documentation](https://tensorflow-object-detection-api-tutorial.readthedocs.io/en/latest/index.html). The following bullet points summarizes the installation steps necessary in order setup the enviornment with links to their locations in the documentation:

#### setup
* [Install Tensorflow](https://tensorflow-object-detection-api-tutorial.readthedocs.io/en/latest/install.html#tensorflow-installation). Both CPU and GPU support is available.
* [Install Tensorflow Models](https://tensorflow-object-detection-api-tutorial.readthedocs.io/en/latest/install.html#tensorflow-models-installation) and complete the following steps in the documentation:
  * Install prerequisites
  * Download the TensorFlow models
  * Protobuf installation/compilation
  * Adding necessary Environment Variables
  * COCO API installation
  * Test installation
* If creating a new dataset, consult the [labelImg installation](https://tensorflow-object-detection-api-tutorial.readthedocs.io/en/latest/install.html#labelimg-installation) and follow the data processing steps outlined in the project report. Alternatively, follow the [documentation](https://tensorflow-object-detection-api-tutorial.readthedocs.io/en/latest/training.html) according to the following steps:
  * Preparing workspace
  * Annotating images
  * Creating label map
  * Creating TensorFlow records (xml to csv and csv to tfrecord)

#### further training
The folders [benchmark](benchmark), [M1](M1) and [M2](M2) are the training directories for three models trained in this project, containing the fine-tuned checkpoints and the model configuration file. When the the Tensorflow object detection environment is installed, these can be downloaded and trained further. Either by using the tfrecords provided in this repository ([data](data)) or with new data. 
Assuming that both Tensorflow and the object detection environment outlined above has been downloaded and setup, the models in this repository can be trained as follows:

  * Download the desired model (e.g. [M2](M2)) and place this folder within the object_detection directory in models/research
  * Download the ([data](data)) directory or alternatively create new data. 
  * Change the paths in the configuration file and run the train-evaluation pipeline as outlined in the methodology chapter of the project report.
  
#### inference and cropping
The inference graph for the M2 model has been frozen and exported so that inference can be done on new core images, as can be seen in the modified object detection tutorial [notebook](inference/object_detection_tutorial_modified.ipynb). The notebook shows inference performed on three optical core images, and the cropped result using the predicted bounding boxes from M2 is saved in the [cropped_output](inference/M2_inference_graph/cropped_output) folder. The notebook and the inference graph can be downloaded and used to perform inference and cropping with the following steps:

  * Download the [inference](inference) folder
  * Move the [notebook](inference/object_detection_tutorial_modified.ipynb) and the [M2_inference_graph](inference/M2_inference_graph) folder into models/research/object_detection
  * Add the optical core images to perform inference on in models/research/object_detection/M2_inference_graph/image
  * Start jupyter notebook from the object_detection directory
  * Perform inference by running the notebook


  

  
