## Introduction to Tensorflow

### Installation of the Nvidia Cuda and CuDNN drivers:

```bash
# For Arch Linux
sudo pacman -Sy cuda cuda-tools cudnn
```

Added the path of the cuda and cudnn packages to the `~/.bashrc` file.

```bash
export CUDA_PATH=/opt/cuda
export PATH=$CUDA_PATH/bin:$PATH
export LD_LIBRARY_PATH=$CUDA_PATH/lib64:/usr/lib64:$LD_LIBRARY_PATH
export CPATH=$CUDA_PATH/include:/usr/include:$CPATH
export LIBRARY_PATH=$CUDA_PATH/lib64:/usr/lib64:$LIBRARY_PATH
```

Caution: This path can vary depending upon your devices.

### Installation of the tensorflow in conda:

Pre-Requirements :

> 1.  Nvidia Cuda Drivers
> 2.  Installed conda / miniconda

```bash
# Creating the conda environment
conda create --name=tf python=3.9
conda activate tf
conda install -c conda-forge cudatoolkit=11.8 cudnn=8

# Adding the cuda and cudnn to the path in the conda environment
mkdir -p $CONDA_PREFIX/etc/conda/activate.d
echo 'export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:$CONDA_PREFIX/lib/' > $CONDA_PREFIX/etc/conda/activate.d/env_vars.sh
```

Sign out and sign back in via SSH or close and re-open your terminal window. Reactivate your conda session.

```bash
# Install the tensorflow with the help of the pip
conda activate tf
python3 -m pip install tensorflow==2.16.1

# Verify install:
python3 -c "import os; os.environ['TF_CPP_MIN_LOG_LEVEL'] = '3'; import tensorflow as tf; print('Num GPUs Available: ', len(tf.config.list_physical_devices('GPU')))"
```

Thus the tensorflow is installed properly along with the GPU support.
