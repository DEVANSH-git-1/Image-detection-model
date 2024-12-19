<img src="https://github.com/user-attachments/assets/e24e8a75-fbd5-44df-88a7-1df1fedfeb06" width="250" height="auto" alt="tensorflow-image-detection icon"/>

The program applies Transfer Learning to this existing model and re-trains it to classify a new set of images.

This is a generic setup and can be used to classify almost any kind of image. I created a small demo that classifies two image data sets - cat and dog images, and returns a prediction score denoting the possibility of it being an image of a cat or a dog.

<br/>

## Installation
Make sure you have [Python 3](https://www.python.org/downloads/) installed, then install [Tensorflow](https://www.tensorflow.org/install/) on your system, and clone this repo.

<br/>

## Usage

### Prepare the image data sets
In order to start the transfer learning process, a folder named ``training_dataset`` needs to be created in the root of the project folder. This folder will contain the image data sets for all the subjects, for whom the classification is to be performed.

Create the ``training_dataset`` folder and add the images for all the data sets in the following manner -

```javascript
/
|
|
---- /training_dataset
|    |
|    |
|    ---- /cat
|    |    cat1.jpg
|    |    cat2.jpg
|    |    ...
|    |
|    |
|    ---- /dog
|         dog1.jpg
|         dog2.jpg
|         ...
|
|     
```
This enables classification of images between the ``cat`` and ``dog`` data sets.

> Make sure to include multiple variants of the subject (side profiles, zoomed in images etc.), the more the images, the better is the result.

### Initiate transfer learning
Go to the project directory and run -

```javascript
$ bash train.sh
```
This script installs the ``Inception`` model and initiates the re-training process for the specified image data sets.

Once the process is complete, it will return a training accuracy somewhere between ``85% - 100%``.

The ``training summaries``, ``retrained graphs`` and ``retrained labels`` will be saved in a folder named ``tf_files``.

### Classify objects

```javascript
python3 classify.py
```

This opens up the file dialog using which you can select your input file.

<img src="https://github.com/user-attachments/assets/3b881e60-9390-4f61-89d5-cc3cb1fcacf1"/>

Once the input file is selected, the classifier will output the predictions for each data set. A prediction score between ``0.8`` to ``1`` is considered to be optimal.


<br/>

## Results
<img src="https://raw.githubusercontent.com/ArunMichaelDsouza/tensorflow-image-detection/master/result.png"/>

<br/>


<br/>



<br/>

## License
MIT License

Copyright (c) 2024 Deavansh-git-1

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.

All training dataset and input images have been taken from [freepik.com](https://www.freepik.com/).

