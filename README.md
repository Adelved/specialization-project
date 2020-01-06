# Specialization Project
This github repository is created as a supplementary resource to my specialization project conducted during the fall of 2019. The focus of the project was to deveolope a Faster R-CNN object detection model using the Tensorflow API in order to detect and localize cores within optical core images used in the petroleum industry. This repository presents the results generated by the three models (benchmark,M1,M2) outlined in the project report. Additonally, the weights from the three models and inference graph from the final model (M2) is made available so that they can be trained further, or be used for inference. 
## Appendix
The [Appendix](Appendix) directory contains the files and scripts mentioned in Methodology chapter of the report ([files](Appendix/scripts)), the [configuration files](Appendix/configuration_files) for the three models, as well as the [data](Appendix/data) used. The original images are provided in .jpeg format and the labeld data is provided in the formats: .xml, .csv and .tfrecord. Additionally, the predictions on the validation set for the three models and the M2 predictions on test set is presented in [prediction_results](Appendix/prediction_results). Notice that some of the images with the predicted bounding boxes are too large to be previewed on github, and must be downloaded in order to be viewed.
The files in the Appendix directory are mainly intented for viewing and not for further use. Thus, the file paths in the configuration files are specific for project structure of the author. 
## Further Training


Welcome to the object detection inference walkthrough!  This notebook will walk you step by step through the process of using a pre-trained model to detect objects in an image. Make sure to follow the [installation instructions](https://github.com/tensorflow/models/blob/master/research/object_detection/g3doc/installation.md) before you start.
