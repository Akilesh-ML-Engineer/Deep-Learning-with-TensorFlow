## Introduction to Tensorflow

### Installation of the tensorflow in conda:

Pre-Requirements :

> 1.  Nvidia Cuda Drivers
> 2.  Installed conda / miniconda

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
- [Introduction to Tensors](https://www.tensorflow.org/guide/tensor)
- [Linear Regression](https://www.tensorflow.org/tutorials/estimator/linear)
- [Best-fit Line in linear regression](https://www.investopedia.com/terms/l/line-of-best-fit.asp)
- “Tf.feature_column.categorical_column_with_vocabulary_list.” TensorFlow, www.tensorflow.org/api_docs/python/tf/feature_column/categorical_column_with_vocabulary_list?version=stable.
- Staff, EasyBib. “The Free Automatic Bibliography Composer.” EasyBib, Chegg, 1 Jan. 2020, www.easybib.com/project/style/mla8?id=1582473656_5e52a1b8c84d52.80301186.
- Seif, George. “The 5 Clustering Algorithms Data Scientists Need to Know.” Medium, Towards Data Science, 14 Sept. 2019, https://towardsdatascience.com/the-5-clustering-algorithms-data-scientists-need-to-know-a36d136ef68.
- Definition of Hidden Markov Model, http://jedlik.phy.bme.hu/~gerjanos/HMM/node4.html.
- “Tfp.distributions.HiddenMarkovModel &nbsp;: &nbsp; TensorFlow Probability.” TensorFlow, www.tensorflow.org/probability/api_docs/python/tfp/distributions/HiddenMarkovModel.
