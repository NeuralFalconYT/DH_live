### **1. Installation with Virtual Environment**

#### **Step 1: Clone the repository**
```bash
git clone https://github.com/NeuralFalconYT/DH_live.git
```

#### **Step 2: Change directory to the project folder**
```bash
cd DH_live
```
and 
```
python make_model.py
```
#### **Step 3: Create a virtual environment**
```bash
python -m venv myenv
```

#### **Step 4: Activate the virtual environment**

**For Windows:**
```bash
myenv\Scripts\activate
```

**For Linux:**
```bash
source myenv/bin/activate
```

#### **Step 5: Install the dependencies**
```bash
pip install -r requirements.txt
```

#### **Step 6: Find your CUDA version**

- For Example CUDA 11.8, run:
```bash
pip install torch --index-url https://download.pytorch.org/whl/cu118
```
(You can adjust the version if you have a different CUDA version)

#### **Step 7: Run the app in debug mode**
```bash
python app.py --debug
```

---

### **2. Installation without Using a Virtual Environment**

#### **Step 1: Clone the repository**
```bash
git clone https://github.com/NeuralFalconYT/DH_live.git
```

#### **Step 2: Change directory to the project folder**
```bash
cd DH_live
```
and 
```
python make_model.py
```
#### **Step 3: Install the dependencies**
```bash
pip install -r requirements.txt
```

#### **Step 4: Find your CUDA version**
[If you already have PyTorch installed, skip Step 4.]
- For Example CUDA 11.8, run:
```bash
pip install torch --index-url https://download.pytorch.org/whl/cu118
```
(You can adjust the version based on your CUDA setup)

#### **Step 5: Run the app in debug mode**
```bash
python app.py --debug
```


# Real-time Live Streaming Digital Human
# 实时直播数字人  [bilibili video](https://www.bilibili.com/video/BV1Ppv1eEEgj/?vd_source=53601feee498369e726af7dbc2dae349)
### News
## Training
Details on the render model training can be found [here](https://github.com/kleinlee/DH_live/tree/master/train).
### Video Example


https://github.com/user-attachments/assets/7e0b5bc2-067b-4048-9f88-961afed12478


## Overview
This project is a real-time live streaming digital human powered by few-shot learning. It is designed to run smoothly on all 30 and 40 series graphics cards, ensuring a seamless and interactive live streaming experience.

### Key Features
- **Real-time Performance**: The digital human can interact in real-time with 25+ fps for common NVIDIA 30 and 40 series GPUs
- **Few-shot Learning**: The system is capable of learning from a few examples to generate realistic responses.
## Usage

### Create Environment and Unzip the Model File 
First, navigate to the `checkpoint` directory and unzip the model file:
```bash
conda create -n dh_live python=3.12
conda activate dh_live
pip install torch --index-url https://download.pytorch.org/whl/cu124
pip install -r requirements.txt
cd checkpoint
```
on Linux
```bash
cat render.pth.gz.001 render.pth.gz.002 > render.pth.gz
gzip -d -c render.pth.gz > render.pth
```
on Windows, use zip software such as 7zip/WinRAR to unzip checkpoint file.
### Prepare Your Video
Next, prepare your video using the data_preparation script. Replace YOUR_VIDEO_PATH with the path to your video:
```bash
python data_preparation.py YOUR_VIDEO_PATH
```
The result (video_info) will be stored in the ./video_data directory.
### Run with Audio File
Run the demo script with an audio file. Make sure the audio file is in .wav format with a sample rate of 16kHz and 16-bit single channel. Replace video_data/test with the path to your video_info file, video_data/audio0.wav with the path to your audio file, and 1.mp4 with the desired output video path:
```bash
python demo.py video_data/test video_data/audio0.wav 1.mp4
```
### Real-Time Run with Microphone
For real-time operation using a microphone, simply run the following command:
```bash
python demo_avatar.py
```

## Acknowledgements 
We would like to thank the contributors of [Wav2Lip](https://github.com/Rudrabha/Wav2Lip), [DINet](https://github.com/MRzzm/DINet), [LiveSpeechPortrait](https://github.com/YuanxunLu/LiveSpeechPortraits) repositories, for their open research and contributions.

## License
This project is licensed under the MIT License.

## Contact
For any questions or suggestions, please contact us at [kleinlee1@outlook.com].
