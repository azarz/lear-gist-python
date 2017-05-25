# lear-gist-python
Python library to extract [A. Torralba's GIST descriptor](http://people.csail.mit.edu/torralba/code/spatialenvelope/).

This is just a wrapper for [Lear's GIST implementation](http://lear.inrialpes.fr/software) written in C. It supports both Python 2 and Python 3 and was tested under Python 2.7.10 and Python 3.4.3 on Linux.

## How to build and install

### Pre-requirements
Following packages must be installed before building and installing `lear-gist-python`.

##### numpy
```shell
$ pip install numpy
```

##### FFTW
[FFTW](http://www.fftw.org/) is required to build lear_gist.

fftw3f librarie and DLL

### Build and install (WINDOWS)

Install using pip.exe
```shell
$ pip install <download path>\lear-gist-python
```

You may need to copy some DLLs in the site-packages directory

## Usage
```python
import gist
import numpy as np

img = ... # numpy array containing an image
descriptor = gist.extract(img)
```

## Scene classification sample
This sample uses [8 Scene Categories Dataset](http://people.csail.mit.edu/torralba/code/spatialenvelope/).

`scikit-learn` and `scikit-image` are required.
```shell
$ pip install scikit-learn scikit-image
```

```shell
cd sample
sh download-8scene.sh
# Extract GIST features from images in "spatial_envelope_256x256_static_8outdoorcategories" directory and save them into "features" directory
python feature_extraction.py spatial_envelope_256x256_static_8outdoorcategories features
# Train and test a multi-class linear classifier by features in "features" directory
python scene_classification.py features
```
