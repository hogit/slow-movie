## Mashup of https://github.com/qubist/SlowMovie and https://github.com/GregDMeyer/IT8951

Why? The larger Waveshare e-paper screens with the IT8951 controller are not included in the Waveshare epd library (epd7in5_V2) that https://github.com/qubist/SlowMovie imports.

---

## First follow the general setup from https://github.com/qubist/SlowMovie

SlowMovie requires [python3](https://www.python.org/). It uses [ffmpeg](https://ffmpeg.org/) via [ffmpeg-python](https://pypi.org/project/ffmpeg-python/) for video processing, and [Pillow](https://python-pillow.org/) for image processing.

```
sudo apt install ffmpeg
pip3 install ffmpeg-python
pip3 install pillow
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
