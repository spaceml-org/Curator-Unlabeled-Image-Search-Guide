## Image Similarity Search Guide

### [How to set up]
**Step 1.** In a command prompt, clone Image Similarity Search repo.
```
git clone https://github.com/spaceml-org/Image-Similarity-Search
```

**Step 2.** Change the current directory to Image Similarity Search folder and download requirements.
```
cd Image-Similarity-Search
pip install -r requirements.txt
```

**Step 3.** Install FAISS package following [this instruction](https://github.com/facebookresearch/faiss/blob/main/INSTALL.md)

&nbsp;

### [How to use]
**Step 1.** In a command prompt, go to Image Similarity Search folder and launch streamlit server.
```
streamlit run app.py
```
Then Image Similarity Search app will pop up in your browser.

**Step 2.** Upload a model file in a .pt or .pth format.

**Step 3.** Enter the absolute path of the dataset you want to use for indexing. The dataset should be organized in [PyTorch ImageFolder](https://pytorch.org/vision/stable/datasets.html#torchvision.datasets.ImageFolder) format.

```
ex)
  Sample_Dataset
        River
	    image01.jpg
	Beach
	    image02.jpg
	    image03.jpg
	Forest
	    image04.jpg
```

**Step 4.** Enter the output embedding size of the model you uploaded in Step 2.

**Step 5.** Enter the number of neighbors. 
ex) If you enter 5, you'll see 5 similar images to the query image you'd upload later.

**Step 6.** Click ```Create Index``` button.

**Step 7.** Once the indexing is done, you can search similar images to any image you pick by uploading the image in the Upload Query Image Section and click ```Search``` button.

&nbsp;

![Image_Similarity_Search](https://user-images.githubusercontent.com/66165810/133855102-272063ec-2a54-40e9-a655-90a20f39937b.gif)

&nbsp;

### **[Sample model & dataset]**

A sample model (uc_merced.pt) is provided in [Image-Similarity-Search/samples/](https://github.com/spaceml-org/Image-Similarity-Search/tree/master/samples) folder and you can download UC Merced Land Use dataset by running these commands:
```
wget http://weegee.vision.ucmerced.edu/datasets/UCMerced_LandUse.zip
unzip -qq UCMerced_LandUse.zip
```
