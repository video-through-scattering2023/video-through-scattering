# See Video Through Optical Scattering Media Using Spatio-temporal Diffusion Models

<p align="center" width="100%">
    <img width="10%" src="./figures/UCF_measurement.gif">
    <img width="10%" src="./figures/UCF_output.gif">
    <img width="20%" src="./figures/VISEM_measurement.gif">
    <img width="20%" src="./figures/VISEM_output.gif">
</p>

<p align="center" width="100%">
    <img width="67%" src="./figures/cover.jpg">
</p>


## Abstract
Optical scattering causes light rays to deviate from their trajectory, posing challenges for imaging through scattering media such as fog and biological tissues. Although diffusion based inverse solvers have been extensively developed for static imaging problems, its extension
to video recovery, especially through highly scattering media, has been an open problem due to the lack of closed form forward model
and the difficulty in exploiting the prior knowledge of the spatio-temporal correlation.
Here we propose using temporal correlations between time-sequential frames in solving the inverse scattering problem. With the video diffusion model fused with a physical formulation of the shower-curtain effect, the statistical correlation between a series of frames and a series of scattered signals is maximally exploited in a spatiotemporal domain. Unlike previous end-to-end approaches only relied on spatial correlation between a scene and a scattered signal at a specific time point, the adaptability of the proposed method is highly extendable to various types of scenes, various thicknesses of scattering media, and varying distances between a target scene and a medium. The use of temporal correlation is shown to be critical to faithfully retrieve high-frequency components which are often missed by inverse operations only in spatial domain. We test the usability of the proposed approach with the video datasets of moving sperm cells. To the best of our knowledge, this is the first attempt to jointly utilize the correlations in both spatial and temporal domains in solving the inverse scattering problem.


## Prerequisites
- python 3.10

- pytorch 1.13.1

- CUDA 11.7

It is okay to use lower version of CUDA with proper pytorch version.

Ex) CUDA 10.2 with pytorch 1.7.0

<br />

## Getting started 

### 1) Clone the repository

```
git clone https://github.com/video-through-scattering2023/video-through-scattering

cd video-through-scattering
```

<br />

### 2) Download pretrained checkpoint and sample videos
From the [link](https://drive.google.com/drive/folders/1-Zu7GL2dooGFJYEO34s9U0J03LKqd6I6?usp=sharing), download the checkpoints and paste it to ./models/, download the samples and paste it to ./scatter samples/
```
mkdir models
mkdir scatter samples
mv {MODEL_DOWNLOAD_DIR}/{CHECKPOINT NAME} ./{models}/
mv {SAMPLE_DOWNLOAD_DIR}/{SAMPLES} ./{scatter samples}/
```
{DOWNLOAD_DIR} is the directory that you downloaded checkpoint to.
{PASTE_DIR} is the directory that you should paste to.

<br />

### 3) Set environment
Install dependencies

```
conda create -n VTS python=3.10

conda activate VTS

pip install -r requirements.txt

pip install torch==1.13.1+cu117 torchvision==0.14.1+cu117 torchaudio==0.13.1 --extra-index-url https://download.pytorch.org/whl/cu117
```

<br />

### 4) Test

```
python test_UCF.py
python test_VISEM.py
```

<br />
