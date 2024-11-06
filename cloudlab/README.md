# CloudLab Experiment Setup Guide
## Setting up CUDA 12.1 on CloudLab machines
yes | ./setup_vllm.sh

## Running the container
sudo docker run --gpus all -it nvidia/cuda:12.1.1-runtime-ubuntu22.04 /bin/bash

## Installing vLLM in the container
apt-get update
apt-get install -y python3 python3-pip
