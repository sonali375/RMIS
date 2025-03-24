**_RMIS AI Analytics_**
------------------------------
This is a post service that requires image in the form of base64 and returns the gauge detection value.

This image is converted to an image format and sent to grounding_dino.py file to perform object detection for Analog Gauge.

It detects the Analog Gauge and gets the cropped image for the gauge.

The cropped image is then sent to grounded_sam.py file for Detection and Segmentation of the Gauge Needle.

The needle coordinates are sent back to gauge_detection.py file. 

Here Image preprocessing is done for getting image clarity.
Using HoughCircle the gauge circle is detected and angle is plotted.
Then OCR is applied upon it to detect the data out of the gauge.

Creating bounding box for each data we get from OCR. 
Then extend lines taking center of gauge and center of bounding box till the gauge circle to get angle for each data.

Interpolate to get the data for rest.

Taking center of gauge and needle coordinate extend the line till gauge circle to get angle of needle.
Interpolate to get the needle value which is the gauge reading.
