# Cat Vs Dog Classifier

#### Aim: To build a Convolution Neural Network (CNN) binary classifier to classify cats and dogs images using keras.

#### _This repository contains:_
  - File Structure of the initial setup
  - Data Pre-processing
  - Training of the 3 deep learning models

#### _File Structure:_
```
CatVDog-Classifier/
|-- datasets
    |-- y0_train
        |-- cat.1.jpg
	.
        |-- cat.4000.jpg
    |-- y0_dev
        |-- cat.4001.jpg
        .
        |-- cat.4500.jpg
    |-- y0_test
        |-- cat.4501.jpg
        .
        |-- cat.5000.jpg
    |-- y1_train
        |-- dog.1.jpg
        .
        |-- dog.4000.jpg
    |-- y1_dev
        |-- dog.4001.jpg
        .
        |-- dog.4500.jpg
    |-- y1_test
        |-- dog.4501.jpg
        .
        |-- dog.5000.jpg
|-- images
    |-- cat1.jpg
    |-- cat2.jpg
    |-- cat3.jpg
    |-- dog1.jpg
    |-- dog2.jpg
    |-- dog3.jpg
|-- CatVSDog09.ipynb
|-- CatVSDog10.ipynb
|-- CatVSDog11.ipynb
|-- Data Pre-processing Binary Classifier.ipynb
```
#### _Main Files:_
Brief description of the files
  - CatVSDog09.ipynb
	- x2 Data Augmentation of the images (1 original + 1 augmented for each image)
	- From scratch approach
    	- Build a 4-layer ConvNet -> Flatten -> Fully Connected layers (with L2 regularization on the last layer)
	- Accuracy:
		- Epochs: 20 | Batch Size: 32 | Train: 97.4% | Test: 83.1%
  - CatVSDog10.ipynb
	- Transfer learning: Loaded pre-trained model VGG16
	- VGG16 -> MAXPOOL -> Flatten -> Fully Connected
	- Accuracy:
		- Epochs: 15 | Batch Size: 64 | Train: 90.3% | Dev: 87.0% | Test: 84.4%
  - CatVSDog11.ipynb
	- Transfer learning: Loaded pre-trained model MobileNetV2
	- MobileNetV2 -> MAXPOOL -> Flatten -> Fully Connected
	- Accuracy:
		- Epochs: 15 | Batch Size: 64 | Train: 96.8% | Dev: 91.1% | Test: 91.6%
  - Data Pre-processing Binary Classifier.ipynb
	- Image Processing
        - Train-dev-test split
        - Resize Images
        - Data Augmentation
	- Generate HDF5 Files    
        - Convert to numpy data
        - Generate H5 Data
        - Check H5 Data
		
#### _Approach Taken:_
1. Download the catVSdog datasets from kaggle https://www.kaggle.com/tongpython/cat-and-dog
2. As the dataset only provides train and test datasets, we will split the test set into half
3. The other half will go to the dev set for notebook CatVSDog10.ipynb and CatVSDog11.ipynb
4. Place the images into ./datasets according to the file structure above
5. Briefly checked the photos and scrap some cats and dogs images from search engine such that these images do not appear in either of the sets
6. Place the images into the ./images folder as shown in the file structure above
7. Run Data Pre-processing Binary Classifier.ipynb to obtain the train, dev and test .h5 datasets
8. Run CatVSDog09.ipynb, CatVSDog10.ipynb and CatVSDog11.ipynb to obtain its accuracy
	
#### _References:_
- Kaggle: https://www.kaggle.com/tongpython/cat-and-dog
- Andrew Ng's Deep Learning Specialisation: https://www.coursera.org/specializations/deep-learning
- Hoang Viet: https://github.com/TheMarvelousWhale/DeepLearning_Basics_AndrewNg_Coursera
