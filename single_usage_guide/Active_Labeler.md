# Active Labeler Guide

## [How to set up]
**Step 1.** Open up your CLI and clone the Active Labeler repo
```
git clone https://github.com/spaceml-org/Active-Labeler.git
```


**Step 2.** Install requirements
```
pip install -r ./Active-Labeler/requirements.txt
```

## [How to use]
**Step 1.** Change config files: ```model_config.yaml``` and ```pipeline_config.yml```
The main changes are the locations of the model file you are using and the refrence image along with the model's embedding size. 
For instance, in our Colab guide, we changed the config files like this:
```
# Edit the config files
import yaml

with open("/content/Active-Labeler/model_config.yaml") as f:
     list_doc = yaml.safe_load(f)

list_doc["encoder"]["encoder_path"] = "/content/RESISC45-imagenet_resnet18.ckpt"
list_doc["encoder"]["e_embedding_size"] = 512

with open("/content/Active-Labeler/model_config.yaml", "w") as f:
    yaml.dump(list_doc, f, default_flow_style=False)


with open("/content/Active-Labeler/pipeline_config.yaml") as f:
     list_doc = yaml.safe_load(f)

list_doc["model"]["model_path"] = "/content/RESISC45-imagenet_resnet18.ckpt"
list_doc["model"]["embedding_size"] = 512
list_doc["seed_dataset"]["ref_img_path"] = "/content/RESISC45/airplane/airplane_001.jpg"

with open("/content/Active-Labeler/pipeline_config.yaml", "w") as f:
    yaml.dump(list_doc, f, default_flow_style=False)
```

**Step 2.**
Run a command in the following format:
```
python3 main.py --config_path {path_to_config.yaml}
```

ex)
```
python3 /content/Active-Labeler/main.py --config_path /content/Active-Labeler/pipeline_config.yaml
```

![active_labeler](https://user-images.githubusercontent.com/66165810/134758246-316cda3f-5e16-47df-ac92-41ae4f154afe.gif)
