# under construction!!!
This is a trial modified from Counting-people-video of Nikhil-Kasukurthi. We are still working on the modification. 


# Tensorflow-video-Recognition-HTML-interface
From the webcam video recognition of tensorflow, we list the recognized object throught each recognition session onto a webpage with the video and record the list of each session into a database. This way you could provide a better user interface and concentrate on the areas where recognition are not going. 

Using the Tensorflow Object detection API, we will be counting the number of people in a video. A frame is extracted every 30 seconds from the video and a forward pass of the model is performed. If a person is found in the video, then the count is increased. 

## Requirements
OpenCV - 3.3.1<br/>
Tornado<br/>
Tensorflow<br/>
Protocol buffer compiler

## Installation instructions
``` bash
# For CPU
pip install tensorflow
# For GPU
pip install tensorflow-gpu
```
For Ubuntu 
``` bash
sudo apt-get install protobuf-compiler 
```
For OSX
```
brew install protobuf
```
Other Libraries
```
pip install opencv-python
pip install tornado # For running the server 
```
Tensorflow object detection API
```
protoc utils/*.proto --python_out=.
```

## Running
If you want to test out the implementaion then you can use the object_detect.py<br/>
```
python object_detect.py --path <path to video>
```

To run the server<br/>
```
python server.py
```

### Instruction to plot bounding boxes
As per the origial implementation of the tensorflow object detection API, the bounding boxes are normalised. To get the original dimensions you need to do the following. 

```
(left, right, top, bottom) = (xmin * im_width, xmax * im_width,
                              ymin * im_height, ymax * im_height)
```
