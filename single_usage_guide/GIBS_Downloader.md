## GIBS Downloader Guide
GIBS Downloader can be run either in conda prompt or google Colab. 
Click [here](https://github.com/spaceml-org/GIBS-Downloader/blob/main/notebooks/GIBS_Downloader_Demo.ipynb) to check out google Colab demo.

&nbsp;

### [How to set up]
**Step 1.** Download Anaconda or Miniconda (Anaconda in this example)

**Step 2.** Create a conda environment and start it

**Step 3.** Run below commands to set up gdal and GIBS Downloader in conda prompt
```
conda install -c conda-forge gdal=3.2.0
pip install git+https://github.com/spaceml-org/GIBS-Downloader.git#egg=GIBSDownloader
```
![image](https://user-images.githubusercontent.com/66165810/134761088-ffce39a9-b655-4a5a-a0bf-71db7606f2f0.png)
![image](https://user-images.githubusercontent.com/66165810/134761102-66420958-61b0-464d-837c-785d4038b4be.png)


&nbsp;

### [How to use]
You can use GIBS Downloader by running a single command like this:
```
gdl 2021-08-01 2021-08-03 "33.693, -118.620" "34.325, -118.126"
```

There are 4 positional arguments that must be included in the command:
| argument | format |
| :------: | :-----: |
| start date | YYYY-MM-DD |
| end date | YYYY-MM-DD |
| bottom-left coordinates | “latitude, longitude” |
| top-right coordinates | “latitude, longitude” |

If you don't know the coordinates of the region you want to get images of, go to google Maps and right click at the spot you want to get the coordinates of.

Check out [GIBS Downloader repo](https://github.com/spaceml-org/GIBS-Downloader) to see more parameters ready for you.

&nbsp;

![GIBS_Conda Prompt1](https://user-images.githubusercontent.com/66165810/132446559-8f1dfaf8-5d26-4cd6-8607-260466adf60e.gif)
