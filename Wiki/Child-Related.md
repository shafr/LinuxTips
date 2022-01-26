# Converting video to a commix

## Extract frames from video:
```
ffmpeg -i input.mkv -r 0.25 output_%04d.png
```

## Convert images to grayscale:
```
for IN in * ; do                                                                                   
echo ${IN}        
        convert ${IN}  -charcoal 3 ${IN}_cha3.png
        convert ${IN} -edge 1 -negate -normalize -colorspace Gray -blur 0x.5 -contrast-stretch 0x50% ${IN}_gray.png
done
```

## Creating comix from PNG files (using imagemagick):
```
montage -density 300 -tile 1x2 -geometry +0+0 *.png convert-res.pdf
```

# Merging multiple images into one pdf with borders:
```
montage -density 300 -tile 1x2 -geometry +0+0 -bordercolor Gray -border 1 -page A4  *.png res.pdf
```
