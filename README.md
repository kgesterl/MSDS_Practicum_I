# MSDS Practicum I: Kaggle LSST Classification Challenge

In partial fulfillment of the requirements for the degree of Master of Science in Data Science at Regis University, 
the following Practicum I Project has been completed. 
The project was to develop a supervised learning neural network that classifies astronomical objects based on 
light variance coming from the source over a specified observation timeframe.

## Scientific Motivation & Telescope Description 

The datasets come from the Kaggle competition, The Photometric LSST Astronomical Time-Series Classification Challenge (PLAsTiCC). This is simulated data that will mirror real data observed by the new Large Synoptic Survey Telescope (LSST) which is planned to achieve first light in 2019 and become fully operational in 2022. The telescope plans to measure the light from millions of time-varying sources (a few examples include cepheids, supernovae, gamma ray bursts, and eclipsing binaries). The advanced engineering for this telescope allows the field of view to achieve 3.5 degrees, while similar telescopes currently operating can only observe about 0.2 degrees. "This means that LSST can make a map of the entire southern sky, resolving details that are smaller than the width of a human hair held at arm's length every 4 nights." With such high resolution, between 20-40 terabytes of data will be generated every night.
Comparatively, every week that the LSST is in its operational stage, it will discover more time-varying light source objects than the Hubble telescope has in its entire lifetime (https://www.kaggle.com/michaelapers/the-plasticc-astronomy-starter-kit). 

As the telescope moves across the sky, different light filters will be used to observe different wavelengths. The telescope is land based, so along with the time-variance, the scientists will deal with atmospheric conditions that could alter the light received. In addition, because many of these objects will be observed for the first time, their redshift values may not be accurately known. Due to all of these non-regularities and the massive rate of data generation it will be very helpful and time saving to automate the classification of certain types of variable objects. Therefore, the data teams working on the LSST proposed the challenge to Kaggle users to come up with the best feature generation and machine learning algorithm to assist them with this future task (arXiv:1810.00001v1). 

## Dataset Description

The datasets provided consist of four CSV files, two containing training data and two with testing data. The main variables in the raw training and testing data files are an object_id, the time stamp of the observation, the passband (the wavelength of light of the measurement), and the flux (the amount of light received with another variable for the error on this reading). The training raw data file size is 58.6 MB. The testing raw data file size is 19.3 GB. The other two files are metadata files for each of the training and testing sets. These files have the object_id which corresponds to the object_id in the raw data files. Also, there are columns for the object’s position in the sky (lateral) and redshift score (distance with measurement error). In the training metadata sample, there is one extra column called ‘target’ which is an integer representing what type of astronomical object is being observed.

## Data Science Task

For this project I chose to use a classification neural network. The first step was to perform exploratory data analysis (PLaSTiCC EDA.ipynb) to understand the features of the training and test data sets. Next, I tried a number of different methods to perform feature generation and selection based on the light curves of each object (PLaSTiCC Feature Selection.ipynb). Finally, I created a simple neural network model using supervised learning from the training set. With the final model, I made predictions for the test set.  I used Python and in Jupyter notebooks to perform all of the analyses.

## Data

The datasets are not uploaded in this repository because of their size (the size of the test set is about 19 GB). All of the data is available via the Kaggle challenge website: https://www.kaggle.com/c/PLAsTiCC-2018 .
