## Mashup of https://github.com/TomWhitwell/SlowMovie and https://github.com/GregDMeyer/IT8951

Why? The larger Waveshare e-paper screens with the IT8951 controller are not included in the Waveshare epd library (epd7in5_V2) that https://github.com/TomWhitwell/SlowMovie imports.

---

## First follow the general setup from https://github.com/TomWhitwell/SlowMovie

SlowMovie requires [Python 3](https://www.python.org). It uses [FFmpeg](https://ffmpeg.org) via [ffmpeg-python](https://github.com/kkroening/ffmpeg-python) for video processing, and [Pillow](https://python-pillow.org) for image processing. [ConfigArgParse](https://github.com/bw2/ConfigArgParse) is used for configuration and argument handling.

```
sudo apt install ffmpeg
sudo pip3 install ffmpeg-python
sudo pip3 install pillow
sudo pip3 install ConfigArgParse
```

---

## Second follow the steps to build IT8951 from https://github.com/GregDMeyer/IT8951

```
pip install -r requirements.txt
pip install ./
```

Finally, you need to compile the Cython code. From the IT8951 directory you can either do

```
python setup.py build_ext --inplace
```

to build the files right in the source tree, or actually install the package with

```
pip3 install ./
```

---

## Third run it

Run IT8951 tests `python test/integration/test.py`.

Run `python3 slowmovie.py`. If everything installed properly, this should start playing `test.mp4`, a clip from Psycho, which is already in the /Videos directory.
