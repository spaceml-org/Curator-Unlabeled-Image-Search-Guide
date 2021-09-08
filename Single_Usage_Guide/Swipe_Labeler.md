## Swipe Labeler

### [How to set up]
**Step 1.** Install python3 and pip.

**Step 2.** Clone Swipe Labeler repo and change directory into Swipe-Labeler.
```
git clone https://github.com/spaceml-org/Swipe-Labeler
cd Swipe-Labeler
```

**(Optional)** Create and activate a virtual environment.
```
#create a virtual environment.
python3 -m venv venv

#activate the virtual environment.
. venv/bin/activate
```

**Step 3.** Install python dependencies
```
pip install -r api/requirements.txt
```

### [How to use]
**Step 1.** Run Swipe Labeler with below form of a command
```
python api/api.py --path_for_unlabeled=(the complete path to your directory of unlabeled images) --batch_size=(optional batch size , default is 5)
```

ex) 
```
python api/api.py --path_for_unlabeled=C:\Users\Tom\Images\Clouds
```

**Step 2.** Swipe Labeler will give you a URL like http://0.0.0.0:5000/. Open the URL in your browser.

**Step 3.** Swipe Labeler will display one image at a time and you should either accept, reject or skip the image. 

To accept an image, click “Accept” or swipe right or press the right arrow on the keyboard. 
To reject an image, click “Reject” or swipe left or press the arrow left key.
To skip an image, click “Skip”

Swipe Labeler will create a folder called ‘Labeled’ which includes subfolders named ‘Labeled_Negative’, ‘Labeled_Positive’ and ‘Unsure’. Rejected images will be moved from the original directory to the ‘Labeled_Negative’ directory. In the same manner, ‘Labeled_Positive’ will have the images you accepted and ‘Unsure’ will have the skipped images.
```
/Parent folder
      /Unlabeled image folder you designated
             Image1.jpg
             Image2.jpg
      /Labeled
            /Labeled_Negative
                  Image3.jpg
                  Image4.jpg
            /Labeled_Positive
                  Image5.jpg
                  Image6.jpg
            /Unsure
                  Image7.jpg
                  Image8.jpg
```

![swipe_labeler_demo](https://github.com/spaceml-org/Swipe-Labeler/raw/main/Swipe-Labeler-Demo.gif)
