### python = 3.10
### Environment Name:
```
wsl-latest-voice-craft
wsl
conda activate wsl-latest-voice-craft
```

#### Best to make sure you have torch installed first, in particular before installing xformers.
#### Don't run this if you already have PyTorch installed.
```
pip install torch==2.0.1 torchvision==0.15.2 torchaudio==2.0.2 --index-url https://download.pytorch.org/whl/cu118
```
### You might need the following before trying to install the packages
```python -m pip install setuptools wheel```
### Then proceed to one of the following
```
python -m pip install -U audiocraft  # stable release
python -m pip install -U git+https://git@github.com/facebookresearch/audiocraft#egg=audiocraft  # bleeding edge
python -m pip install -e .  # or if you cloned the repo locally (mandatory if you want to train).
python -m pip install -e '.[wm]'  # if you want to train a watermarking model
```
```bash 
sudo apt-get install ffmpeg
```
### Or if you are using Anaconda or Miniconda
```conda install "ffmpeg<5" -c conda-forge```