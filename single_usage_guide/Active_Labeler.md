## Active Labeler Guide
This is a CLI guide for Active Labeler. If you want to check out the Colab notebook guide, click [here.](https://github.com/spaceml-org/Curator-Unlabeled-Image-Search-Guide/blob/main/notebooks/Active_Labeler.ipynb)

&nbsp;

### [How to set up]
**Step 1.** Open up your CLI and clone the Active Labeler repo
```
git clone https://github.com/spaceml-org/Active-Labeler.git
```


**Step 2.** Install requirements
```
pip install -r ./Active-Labeler/requirements.txt
```

&nbsp;

### [How to use]
**Step 1.** Change [model_config.yaml](https://github.com/spaceml-org/Active-Labeler/blob/main/model_config.yaml) file and [pipeline_config.yml](https://github.com/spaceml-org/Active-Labeler/blob/main/pipeline_config.yaml) file according to the model and dataset you want to use. The main changes will be the locations of the model file and the refrence image file along with the model's embedding size and the image size used for training the model. 

&emsp; &emsp; **[model_config.yaml]**

&emsp; &emsp; <img width="640" alt="snapshot button" src="https://user-images.githubusercontent.com/66165810/134760273-8366e625-9bca-4694-bd3b-b711c43ef875.PNG">

&emsp; &emsp; **[pipeline_config.yaml]**

&emsp; &emsp; <img width="640" alt="snapshot button" src="https://user-images.githubusercontent.com/66165810/134760236-3ce45a43-21e9-4b2a-bbfd-49eb538b28c0.PNG">


**Step 2.**
Run a command in the following format:
```
python3 main.py --config_path {path_to_config.yaml}
```

ex)
```
python3 /content/Active-Labeler/main.py --config_path /content/Active-Labeler/pipeline_config.yaml
```

&nbsp;

![active_labeler](https://user-images.githubusercontent.com/66165810/134758246-316cda3f-5e16-47df-ac92-41ae4f154afe.gif)
