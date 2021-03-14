```bash
conda create --name tf --yes python=3.8
conda activate tf
pip3 install tensorflow==2.4
pip install jupyterlab
python -m ipykernel install --user --name tf --display-name "Python 3.8 (tf)"
jupyter-lab
```
