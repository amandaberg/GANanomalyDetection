# Unsupervised Learning of Anomaly Detection from Contaminated Image Data using Simultaneous Encoder Training

This repo contains the source code presented in the ArXiV paper with the same name:

A. Berg, J. Ahlberg, and M. Felsberg, Unsupervised Learning of Anomaly Detection from Contaminated Image Data using Simultaneous Encoder Training, https://arxiv.org/abs/1905.11034, (2019)

## About the Code

The source code is an altered version of the Tensorflow version of the "Progressive Growing of GANS" code [1].

More information on system requirements, how to import and use pre-trained networks, how to prepare your own datasets etc. can be found here:
https://github.com/tkarras/progressive_growing_of_gans

## How to run the code
1) Open config.py
2) Alter the file depending on what you want to do (see below)
3) Run train.py

### Training
Start by making sure that all rows below header "Utility scripts" are commented. Put your dataset in the dataset folder (need to be in .tfrecord format). I have included an mnist dataset as an example. Again, if you want to use another dataset, see https://github.com/tkarras/progressive_growing_of_gans for more information on how to pre-process training data. I have added a few functions in dataset_tool.py for MNIST, LSUN, CIFAR etc. In contrast to the functions in the original dataset_tool.py they also export validation data as .png's.

Rows 60 to 102 show a bunch of examples on how to configure which dataset to use. If you want to train with the example mnist dataset, just leave the following line uncommented:

```
desc += '-mnist_2_0.0';               dataset = EasyDict(tfrecord_dir='mnist_2_0.0')
```

### Anomaly detection
Uncomment the anomaly detection example in config.py (row 153) and edit run_id (the id of the folder where the results are saved) and test_data_folder. The test_data_folder should contain .png files of the same dimensions as the images used for training.

## MNIST example dataset
I have included an example dataset. Unpack the dataset.zip folder in order to use it. In this dataset, MNIST number 2 is considered to be normal samples and all other numbers anomalies. There are no anomalies in the training data.

## Finally
Don't hesitate to contact me if you have any questions. Happy coding!

## References
[1] T. Karras, T. Aila, S. Laine, and J. Lehtinen. Progressive Growing of GANs for Improved Quality, Stability,
and Variation. In ICLR 2018, oct 2017.
