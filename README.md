# Object-Detection-using-STM32-board

Setting up TensorFlow Lite on the Raspberry Pi :

1. Update the Raspberry Pi.
2. Download this repository and create a virtual environment.
3. Install TensorFlow and OpenCV.
4. Set up the TensorFlow Lite detection model.
5. Run the TensorFlow Lite model !

Step1 : **Update the Raspberry Pi by running the following commands in the terminal:**

```
sudo apt-get update
sudo apt-get upgrade
```

Step2 : **Make sure the camera interface is enabled in Raspberry Pi Configuration menu.**

Step3 : **Download this repository and create virtual environment**

```
git clone https://github.com/pointarcher02/Object-Detection-using-STM32-board.git

```

We can rename it for simplying purposes such as

```
mv Object-Detection-using-STM32-board tflite1
cd tflite1

```

Step4 :  **Create A Virtual Environment**

We will be using a virtual environment for this guide because it prevents any conflicts between versions of package libraries that may already be installed on your Pi. By keeping TensorFlow installed in its own environment, we can avoid version conflicts and ensure that everything works smoothly.

Install virtual-env by issuing:

```
sudo pip3 install virtualenv


```

Then, create the "tflite1-env" virtual environment by issuing:

```
python3 -m venv tflite1-env

```

Activate the environment:

```
source tflite1-env/bin/activate

```

Step5 :  **Install TensorFlow Lite dependencies and OpenCV**

```
bash get_pi_requirements.sh

```

Step6 : **Set up TensorFlow Lite detection model**

**Using Google's sample TFLite model**

Google provides a sample quantized SSDLite-MobileNet-v2 object detection model which is trained off the MSCOCO dataset and converted to run on TensorFlow Lite. It can detect and identify 80 different common objects, such as people, cars, cups, etc.

Download the sample model by issuing:

```
wget https://storage.googleapis.com/download.tensorflow.org/models/tflite/coco_ssd_mobilenet_v1_1.0_quant_2018_06_29.zip

```

Unzip it to a folder called "Sample_TFLite_model" by issuing (this command automatically creates the folder):

```
unzip coco_ssd_mobilenet_v1_1.0_quant_2018_06_29.zip -d Sample_TFLite_model

```

Step7 : **Run TensorFlow Lite detection model.**

The TFLite_detection_webcam.py script will work with either a Picamera or a USB webcam.

```
python3 TFLite_detection_webcam.py --modeldir=Sample_TFLite_model

```
