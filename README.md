## Tracking algorithm

### Environment Setup on Ubuntu 18.04
1) Install cuda v11 [toolkit](https://developer.nvidia.com/cuda-downloads?target_os=Linux&target_arch=x86_64&Distribution=Ubuntu&target_version=18.04&target_type=deb_local)
2) Install Anaconda [link](https://www.anaconda.com/products/individual#linux)



### Python Environment Setup
1) Activate Intel Distribution for Python (idp): `conda activate idp`<br>
2) Install Python dependencies `pip3 install -r requirements.txt ` to install required dependencies <br>
3) Add `export PYTHONPATH=$PYTHONPATH:/project_root` to `~/.bashrc` <br>

NOTE: Make sure you install an opencv-python version that was compiled with ffmpeg flag to be able to read .mpg video files.


### Using the algorithm
1) Download Sample [video](https://drive.google.com/drive/folders/1TQiYoiA1uMNZHRfJPVhJXa6p-TgNV2PX?usp=sharing), [calibration files](https://drive.google.com/file/d/1Pll2jAHzyQONjZ6ThRXL4I-WMVeCfhN7/view?usp=sharing) and re-trained [model](https://www.dropbox.com/s/0j1051ie3otb77e/retrained_net.pth?dl=0)
2) The project must have the following folder structure:

```
tracking_3d
│   README.md
|   requirements.txt
│   tracking.py
|   ...
|   retrained_net.pth
│
└───data
│   │   video
│   │   calibration_2d

```
3) Change the folder path in `main` function within `tracking.py` file to point to the data folder of the project
4) The tracking algorithm can be used to either extract or replay trajectories from the video. To extract tracking data, set flag `replay=False` within the `test_tracker()` method. To replay tracking data, set flag `replay=True` within the `test_tracker` method.
5) Choose the format of the data extracted by selecting `npy` or `csv` within the `test_tracker` method
6) Run `python3 tracking.py`


### References
If you find this algorithm useful for your work, please cite it as follows: <br>

  <a href="https://arxiv.org/abs/2104.00893"> Duo Lu, Varun C Jammula, Steven Como, Jeffrey Wishart, Yan Chen, & Yezhou Yang. (2021). CAROM – Vehicle Localization and Traffic Scene Reconstruction from Monocular Cameras on Road Infrastructures. </a>
