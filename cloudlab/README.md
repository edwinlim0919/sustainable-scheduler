# CloudLab Experiment Setup Guide
## Setting up CUDA 12.1 on CloudLab machines
yes | ./setup_vllm.sh

## Running the container
sudo docker run --gpus all -it nvidia/cuda:12.1.1-runtime-ubuntu22.04 /bin/bash

## Installing vLLM in the container
apt-get update
apt-get install -y python3 python3-pip
apt-get install -y build-essential libpython3-dev
pip3 install --upgrade pip setuptools wheel
pip3 install numpy torch
pip3 install vllm
python3 -c "import vllm; print('vLLM installed successfully!')"

## Install Conda in the container
apt-get install curl
curl -LO https://github.com/conda-forge/miniforge/releases/latest/download/Miniforge3-Linux-aarch64.sh
bash Miniforge3-Linux-aarch64.sh -u -b -p /opt/conda
export PATH="/opt/conda/bin:$PATH"
echo 'export PATH="/opt/conda/bin:$PATH"' >> ~/.bashrc
source ~/.bashrc

## Install vLLM using Conda in the container
conda create -n myenv python=3.10 -y
conda init
source /opt/conda/etc/profile.d/conda.sh
conda activate myenv
pip install vllm 
