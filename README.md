## Introduction to Tensorflow

### Installation of the tensorflow in conda:

Pre-Requirements :

> > 1.  Nvidia Cuda Drivers
> > 2.  Installed conda / miniconda

```
# Creating the conda environment
conda create --name=tf python=3.9
conda activate tf
conda install -c conda-forge cudatoolkit=11.8 cudnn=8

# Adding the cuda and cudnn to the path in the conda environment
mkdir -p $CONDA_PREFIX/etc/conda/activate.d
echo 'export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:$CONDA_PREFIX/lib/' > $CONDA_PREFIX/etc/conda/activate.d/env_vars.sh
```

Sign out and sign back in via SSH or close and re-open your terminal window. Reactivate your conda session.

```
# Install the tensorflow with the help of the pip
conda activate tf
python3 -m pip install tensorflow==2.16.1

# Verify install:
python3 -c "import os; os.environ['TF_CPP_MIN_LOG_LEVEL'] = '3'; import tensorflow as tf; print('Num GPUs Available: ', len(tf.config.list_physical_devices('GPU')))"
```

Thus the tensorflow is installed properly along with the GPU support.

### Documentation

- [Installing the Tensorflow](https://www.tensorflow.org/install/pip)
- [Official Documentation](https://www.tensorflow.org/tutorials?authuser=2)
