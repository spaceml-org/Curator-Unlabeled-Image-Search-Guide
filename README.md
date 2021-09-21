![curator_banner](https://user-images.githubusercontent.com/66165810/132762978-895e7c3c-4377-47ab-bbce-72bc17e94f79.png)

# Curator, the guide
This is a guide for SpaceML’s machine learning pipeline that has seven components:  GIBS Downloader, Self-Supervised Learner (SSL), Image Similarity Search, Index & Search (GCP), Worldview Search Chrome Extension, Swipe Labeler and Active Labler. Each program serves a different role in the pipeline from downloading satellite images and labeling images to training a machine learning model, improving an existing model and doing image similarity search. These programs can be used altogether but you can also utilize just one of them or a few of them according to your needs. Throughout this guide, we will showcase a few ways to combine this pipeline.

## Program description & guide
### 1. [GIBS Downloader](https://github.com/spaceml-org/GIBS-Downloader)
A tool for downloading Earth images. You can download NASA satellite imagery of certain areas and certain time periods that you designate. It is useful to build an Earth image dataset.
  * [Colab guide](https://github.com/spaceml-org/GIBS-Downloader/blob/main/notebooks/GIBS_Downloader_Demo.ipynb)
  * [CLI guide](https://github.com/spaceml-org/Curator-the-guide/blob/main/Single_Usage_Guide/GIBS_Downloader.md)

### 2. [Self-Supervised Learner (SSL)](https://github.com/spaceml-org/Self-Supervised-Learner)
Self-supervised learning program for training a machine learning model with fewer labeled data. You can train an encoder with unlabeled data and train a classifier with less labeled data compared to supervised learning.
  * [Colab guide](https://github.com/spaceml-org/Self-Supervised-Learner/blob/simsiam/tutorials/PythonColabTutorial_Merced.ipynb)

### 3. [Image Similarity Search](https://github.com/spaceml-org/Image-Similarity-Search)
Reverse image search app. Once you have a dataset and a model trained on the dataset, Image Similarity Search can calculate similarities between images in the dataset and show you similar images within the dataset to an image you pick. This can be used for a sanity check to make sure your model is trained well.
  * [Guide](https://github.com/spaceml-org/Curator-Unlabeled-Image-Search-Guide/blob/main/Single_Usage_Guide/Image_Similarity_Search.md)

### 4. [Index & Search (GCP)](https://github.com/spaceml-org/Scalable-Similarity-Search-with-GCP)
‘Image Similarity Search’ app works well with up to 3 million images. If you have a bigger dataset than that, Index & Search (GCP) is recommended for similarity search. It uses Google Cloud Platform which allows for larger storage.
  * [Guide] - Coming soon

### 5. [Swipe Labeler](https://github.com/spaceml-org/Swipe-Labeler)
GUI based image labeling program. You can easily label images by swiping right/left, clicking accept/reject, or pressing the right/left arrow key on the keyboard. Multiple people can use Swipe Labeler at the same time without overwriting labels so you can enjoy speedy labeling with your teammates.  
  * [Guide](https://github.com/spaceml-org/Curator-the-guide/blob/main/Single_Usage_Guide/Swipe_Labeler.md)

### 6. [Active Labeler](https://github.com/spaceml-org/Active-Labeller)
A program designed to better your model in an efficient manner. Once you have a trained model, Active Labeler will pick out images that the model has the most difficulty with. Then you’ll label those images through Swipe Labeler and retrain the model with the newly labeled images so that the model can overcome its weakness.
  * [Colab guide] - Coming soon
  * [CLI guide] - Coming soon

### 7. [Worldview Search Chrome Extension](https://github.com/spaceml-org/Worldviewsearch-Chrome-Extension)
A chrome extension for finding similar images in the [NASA Worldview website](https://worldview.earthdata.nasa.gov/). Take a snapshot of a particular scene in a satellite image on the website. Then our extension will show you similar satellite images to the chosen image.
  * [Guide](https://github.com/spaceml-org/Curator-the-guide/blob/main/Single_Usage_Guide/Worldview_Chrome_Extension.md)

## Combination guide
- [GIBS Downloader + SSL](https://github.com/spaceml-org/Curator-Unlabeled-Image-Search-Guide/blob/main/%5BCurator%5D_GIBS_Downloader_%26_Self_Supervised_Learner.ipynb)
- [SSL + Image Similarity Search + Swipe Labeler + Active Labeller] - Coming soon
