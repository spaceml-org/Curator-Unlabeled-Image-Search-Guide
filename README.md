# Curator, the guide
This is a guide for SpaceML’s machine learning pipeline that has seven components:  GIBS Downloader, SSL Learner, Image Similarity Search, Index & Search (GCP), Worldview Search Chrome Extension, Swipe Labeler and Active Learner. Each program serves a different role in the pipeline from downloading satellite images and labeling images to training a machine learning model, improving an existing model and doing image similarity search. These programs can be used altogether but you can also utilize just one of them or a few of them according to your needs. Throughout this guide, we will showcase a few ways to combine this pipeline.

## Description of each program
### 1. GIBS Downloader
A tool for downloading Earth images. You can download NASA satellite imagery of certain areas and certain time periods that you designate. It is useful to build an Earth image dataset.

* [GIBS Downloader repo](https://github.com/spaceml-org/GIBS-Downloader)
* [Colab demo example](https://github.com/spaceml-org/GIBS-Downloader/blob/main/notebooks/GIBS_Downloader_Demo.ipynb)

### 2. Self Supervised Learner
Self-supervised learning program for training a machine learning model with fewer labeled data. You can train an encoder with unlabeled data and train a classifier with less amount of labeled data compared to supervised learning.
* [Self Supervised Learner repo](https://github.com/spaceml-org/Self-Supervised-Learner)
* [Colab demo example](https://github.com/spaceml-org/Self-Supervised-Learner/blob/simsiam/tutorials/PythonColabTutorial_Merced.ipynb)

### 3. Image Similarity Search
Reverse image search app. Once you have a dataset and a model trained on the dataset, Image Similarity Search can calculate similarities between images in the dataset and show you similar images within the dataset to an image you pick. This can be used for a sanity check to make sure if your model is trained well.
* [Image Similarity Search repo](https://github.com/spaceml-org/Image-Similarity-Search)

### 4. Index & Search (GCP)
‘Image Similarity Search’ app works well with up to 3 million images. If you have a bigger dataset than that, Index & Search (GCP) is recommended for similarity search. It uses Google Cloud Platform which allows you to have bigger storage.
* [Index & Search (GCP) repo](https://github.com/spaceml-org/Scalable-Similarity-Search-with-GCP)

### 5. Swipe Labeler
GUI based image labeling program. You can easily label images by swiping right/left, clicking accept/reject, or pressing the right/left arrow key on the keyboard. Multiple people can use Swipe Labeler at the same time without overwriting labels so you can enjoy speedy labeling with your teammates.  
* [Swipe Labeler repo](https://github.com/spaceml-org/Swipe-Labeler)

### 6. Worldview Search Chrome Extension
A chrome extension for finding similar images in [NASA Worldview website](https://worldview.earthdata.nasa.gov/). Take a snapshot of a particular scene in a satellite image on the website. Then our extension will show you similar satellite images to the chosen image.
* [Worldview Search Chrome Extension repo](https://github.com/spaceml-org/Worldviewsearch-Chrome-Extension)

### 7. Active Learner
A program designed to better your model in an efficient manner. Once you have a trained model, Active Learner will pick out specific images that the model has the most difficulty with. Then you’ll label those images on and retrain the model with the newly labeled images so that the model can overcome its weakness.
* Active Learner repo (coming soon)
