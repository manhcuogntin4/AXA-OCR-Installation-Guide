# OCR-Installation-Guide
Step 1 Install Caffe

Step 1.1 : Login AWS console

Step 1.2 : Choose AMI type Ubuntu16.04 and GPU g2.2xlarge



Step 1.3a : Install Cuda and Cudnn
http://stackoverflow.com/questions/41117980/cant-install-cudnn-5-1-5-with-cuda-8-0-and-tensorflow-0-12-on-g2-2xlarge-instan

Step 1.3b : Install Caffe
https://github.com/BVLC/caffe/wiki/Ubuntu-16.04-or-15.10-Installation-Guide



Step 2 Install Clstm

https://github.com/tmbdev/clstm

and clstm python 

(Error locale-error-setting)
http://stackoverflow.com/questions/14547631/python-locale-error-unsupported-locale-setting

https://jbaiter.github.io/clstm/#installation

Test if pyclstm successful install 
>>python
>>import pyclstm

Step 3 Install Tesseract & PythonTesseract
Step 3a Install Tesseract
sudo apt-get install tesseract-ocr
Step 3b Install python tesseract
pip install pytesseract

Install easydict and python-openCV
sudo apt-get install python-opencv

Step 4 :
Upload axa-code to ec2 instance.
cd to caffe-faster-rcnn
config the file Makefile.config like file Makefile.config in caffe setup
cd to Caffe root
run two command
./scripts/download_model_binary.py models/bvlc_reference_caffenet
./data/ilsvrc12/get_ilsvrc_aux.sh

Step 5: 
Change the rule to make port 80 avaiable for ec2 instance
    Go to the "Network & Security" -> Security Group settings in the left hand navigation
    Find the Security Group that your instance is apart of
    Click on Inbound Rules
    Use the drop down and add HTTP (port 80)
    Click Apply and enjoy

Step 6:
Install imagemagick
sudo apt-get install imagemagick

Step 7: Optional
Install aws configure for copy file between aws and ec2

$> aws configure

Access key id : <acces key>

Secret Access Key : <secret access key>

Zone : eu-west-1

Format : json

