# Extract frames from video:
```
ffmpeg -i input.mkv -r 0.25 output_%04d.png
```


# Creating comix from PNG files (using imagemagick):
```
montage -density 300 -tile 1x2 -geometry +0+0 *.png convert-res.pdf
```
