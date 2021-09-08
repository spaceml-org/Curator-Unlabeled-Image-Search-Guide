## GIBS Downloader
GIBS Downloader can be run either in conda prompt or google Colab. Click [here](https://github.com/spaceml-org/GIBS-Downloader/blob/main/notebooks/GIBS_Downloader_Demo.ipynb) to check out google Colab demo.


**Step 1.** Download Anaconda or Miniconda (Anaconda in this example)

**Step 2.** Create a conda environment and start it

**Step 3.** Run below commands to set up gdal and GIBS Downloader in conda prompt
```
conda install -c conda-forge gdal=3.2.0
pip install git+https://github.com/spaceml-org/GIBS-Downloader.git#egg=GIBSDownloader
```
**Step 4.** To download satellite images, write a command including 4 positional arguments (start-date, end-date, bottom-left-coordinates, top-right-coordinates) and hit enter. 

ex) 
```
gdl 2021-08-01 2021-08-03 "33.693, -118.620" "34.325, -118.126"
```
Dates should be entered as YYYY-MM-DD and coordinates should be entered as “latitude, longitude”
You can go to google Maps and right click the spot you want to get the coordinates of.

![GIBS_Conda Prompt1](https://user-images.githubusercontent.com/66165810/132446559-8f1dfaf8-5d26-4cd6-8607-260466adf60e.gif)


**(Optional) Step 5.** If you want to download tiled images of the desired region, add --tile=true to the command. You can also use arguments like --tile-width and --tile-height to set the tile size.
