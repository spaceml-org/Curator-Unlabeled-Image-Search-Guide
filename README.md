![curator_banner](https://user-images.githubusercontent.com/66165810/132762978-895e7c3c-4377-47ab-bbce-72bc17e94f79.png)

# Curator, the guide
This is a guide for SpaceML’s machine learning pipeline that has seven components which are summarized below. Each program serves a different role in the pipeline from downloading satellite images and labeling images to training a machine learning model, improving an existing model and doing image similarity search. These programs can be used altogether but you can also utilize just one of them or a few of them according to your needs. Throughout this guide, we will showcase a few ways to combine this pipeline.

## Program description & guide
### 1. [GIBS Downloader](https://github.com/spaceml-org/GIBS-Downloader)
A tool for downloading Earth images. You can download NASA satellite imagery of certain areas and certain time periods that you designate. It is useful to build an Earth image dataset.
  * [Colab guide](https://github.com/spaceml-org/GIBS-Downloader/blob/main/notebooks/GIBS_Downloader_Demo.ipynb)
  * [CLI guide](https://github.com/spaceml-org/Curator-Unlabeled-Image-Search-Guide/blob/main/single_usage_guide/GIBS_Downloader.md)

### 2. [Self-Supervised Learner (SSL)](https://github.com/spaceml-org/Self-Supervised-Learner)
Self-supervised learning program for training a machine learning model with fewer labeled data. You can train an encoder with unlabeled data and train a classifier with less labeled data compared to supervised learning.
  * [Colab guide](https://github.com/spaceml-org/Self-Supervised-Learner/blob/simsiam/tutorials/PythonColabTutorial_Merced.ipynb)

### 3. [Image Similarity Search](https://github.com/spaceml-org/Image-Similarity-Search)
Reverse image search app. Once you have a dataset and a model trained on the dataset, Image Similarity Search can calculate similarities between images in the dataset and show you similar images within the dataset to an image you pick. This can be used for a sanity check to make sure your model is trained well.
  * [Guide](https://github.com/spaceml-org/Curator-Unlabeled-Image-Search-Guide/blob/main/single_usage_guide/Image_Similarity_Search.md)

### 4. [Index & Search (GCP)](https://github.com/spaceml-org/Scalable-Similarity-Search-with-GCP)
‘Image Similarity Search’ app works well with up to 3 million images. For the scalable image similarity search with bigger dataset, we used Index & Search (GCP), which utilizes Google Cloud Platform. To begin with, we saved the dataset and model we got from GIBS Downloader and Self-Supervised Learner on Google Cloud Storage Bucket. Then we had ①Index API and ②Search API. With Index API, we generated embeddings, an indexer file and a metadata file in Google Compute Engine VM. NVIDA DALI and FAISS were used to make the process more efficient. Then we deployed the Search API, which was built using FastAPI for minimal latency, to Google App Engine for the live image similarity search. Google Cloud Functions helped with easy and smooth usage of GCP throughout the process. To get a glimpse of how Index API works, check out [this sample notebook](https://github.com/spaceml-org/Curator-Unlabeled-Image-Search-Guide/blob/main/notebooks/Index_API_Demo.ipynb)

### 5. [Swipe Labeler](https://github.com/spaceml-org/Swipe-Labeler)
GUI based image labeling program. You can easily label images by swiping right/left, clicking accept/reject, or pressing the right/left arrow key on the keyboard. Multiple people can use Swipe Labeler at the same time without overwriting labels so you can enjoy speedy labeling with your teammates.  
  * [Guide](https://github.com/spaceml-org/Curator-Unlabeled-Image-Search-Guide/blob/main/single_usage_guide/Swipe_Labeler.md)

### 6. [Active Labeler](https://github.com/spaceml-org/Active-Labeller)
A program designed to better your model in an efficient manner. Once you have a trained model, Active Labeler will pick out images that the model has the most difficulty with. Then you’ll label those images through Swipe Labeler and retrain the model with the newly labeled images so that the model can overcome its weakness.
  * [Colab guide] - Coming soon
  * [CLI guide] - Coming soon

### 7. [Worldview Search Chrome Extension](https://github.com/spaceml-org/Worldviewsearch-Chrome-Extension)
A chrome extension for finding similar images in the [NASA Worldview website](https://worldview.earthdata.nasa.gov/). Take a snapshot of a particular scene in a satellite image on the website. Then our extension will show you similar satellite images to the chosen image.
  * [Guide](https://github.com/spaceml-org/Curator-Unlabeled-Image-Search-Guide/blob/main/single_usage_guide/Worldview_Chrome_Extension.md)

## Combination guide
### 1. [GIBS Downloader](https://github.com/spaceml-org/GIBS-Downloader) + [Self-Supervised Learner](https://github.com/spaceml-org/Self-Supervised-Learner)
  * [Guide](https://github.com/spaceml-org/Curator-Unlabeled-Image-Search-Guide/blob/main/notebooks/GIBS_Downloader%2BSelf_Supervised_Learner.ipynb)
### 2. [Self-Supervised Learner](https://github.com/spaceml-org/Self-Supervised-Learner) + [Image Similarity Search](https://github.com/spaceml-org/Image-Similarity-Search) + [Active Labeler](https://github.com/spaceml-org/Active-Labeller)
  * [Guide](https://github.com/spaceml-org/Curator-Unlabeled-Image-Search-Guide/blob/main/notebooks/SSL%2BImage_Similarity_Search%2BActive_Labeler.ipynb)
