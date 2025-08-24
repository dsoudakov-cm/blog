Title: Deploying an EC2 Instance with Ubuntu and NVIDIA Support
Date: 2024-04-17
Category: Notes
Tags: AWS, EC2, NVIDIA, Ubuntu
Slug: deploy-ec2-instance-ubuntu-nvidia
Authors: DS and GPT4
Summary: Step-by-step guide to deploying an EC2 instance using latest (as of today) Ubuntu 22.04 LTS and setting up NVIDIA drivers.

## Introduction

This guide will walk you through the steps to deploy an Amazon EC2 instance using the `p3.2xlarge` type with an AMI provided by Canonical for Ubuntu 22.04 LTS (Jammy Jellyfish). This setup is particularly useful for applications requiring GPU capabilities, such as machine learning and video processing.

## Prerequisites

- An AWS account
- Basic knowledge of Linux commands and AWS management

## Deployment Steps

### Step 1: Launch the EC2 Instance

Start by launching an EC2 instance with the following specifications:

- **Instance Type:** `p3.2xlarge`
- **AMI ID:** `ami-05d4121edd74a9f06` (Canonical, Ubuntu, 22.04 LTS, amd64 jammy image build on 2024-03-01)

### Step 2: Initial Setup

Once the instance is running, connect to it via SSH and execute the following commands as a superuser (`sudo su -`):

```bash
apt update
apt upgrade -y
reboot
apt install amazon-ec2-utils awscli nvtop -y -q
apt install ffmpeg nvidia-utils-545 python3-pip python3.10-venv -y -q
```
### To enable GPU processing, install the NVIDIA drivers:
```bash
curl https://us.download.nvidia.com/tesla/550.54.15/NVIDIA-Linux-x86_64-550.54.15.run -o nvidia.run
chmod +x nvidia.run
./nvidia.run --silent
```

### Install software required for video processing and Python environment management:
```bash
python3 -m venv env1
. ./env1/bin/activate
pip install nvidia-cudnn-cu12 nvidia-cudnn-cu11==8.9.6.50 -y -q
export LD_LIBRARY_PATH=`python3 -c 'import os; import nvidia.cublas.lib; import nvidia.cudnn.lib; print(os.path.dirname(nvidia.cublas.lib.__file__) + ":" + os.path.dirname(nvidia.cudnn.lib.__file__))'`
```

### Test using faster-whiser
```bash
pip -q install faster-whisper-cli
pip -q install git+https://github.com/dsoudakov/python_modules.git@main#subdirectory=youtube_audio
youtube-audio https://www.youtube.com/watch?v=XlTz-TmrLJg
faster-whisper yt_audio.mp3 -o yt1.txt --vad_filter 1 --model_size_or_path large-v3
```