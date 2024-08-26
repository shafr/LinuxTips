We'll be using this project to create subtitles:

```
sudo add-apt-repository ppa:deadsnakes/ppa
sudo apt install python3.9
apt install python3.9-venv

git clone https://github.com/Carleslc/AudioToText
```

Then run it again to istall all deps:
```
python audiototext.py --model medium --deepl_formality informal  --language Enlgish input.aac --output_dir output_dir
```

If you want to use GPU, you would need to uninstall libs and install gpu based libs from https://pytorch.org/:
```
pip uninstall torch
pip uninstall numpy
pip3 install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu118
```

Now you are ready to run command:
```
python audiototext.py --model medium --skip-install --deepl_formality informal  --language Enlgish input.aac --output_dir output_dir
```

