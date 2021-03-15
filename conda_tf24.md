# Install TensorFlow 2.4 in Conda env

## Normal
```bash
conda create --name tf --yes python=3.8
conda activate tf
pip3 install tensorflow==2.4
pip install jupyterlab
python -m ipykernel install --user --name tf --display-name "Python 3.8 (tf)"
jupyter-lab
```

## MacOS (M1)
```bash
wget https://github.com/conda-forge/miniforge/releases/latest/download/Miniforge3-MacOSX-arm64.sh
sh Miniforge3-MacOSX-arm64.sh

/your/miniforge/path/bin/activate

conda create --name tf_macos_m1 --yes python=3.8
conda activate tf_macos_m1
```
https://github.com/apple/tensorflow_macos
```bash
# Install tensorflow to directory /your/home/path/.conda/envs/tf_macos_m1
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/apple/tensorflow_macos/master/scripts/download_and_install.sh)"

# scipy, numpy, https://github.com/numpy/numpy/issues/17807
/your/homebrew/path/bin/brew install openblas
OPENBLAS="$(/your/homebrew/path/bin/brew --prefix openblas)" pip3 install -U numpy scipy

pip install jupyterlab
python -m ipykernel install --user --name tf_macos_m1 --display-name "Python 3.8 (tf_macos_m1)"

jupyter-lab
```

## Remove Jupyter Kernel
```bash
jupyter kernelspec uninstall unwanted-kernel
```
