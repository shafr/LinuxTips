To print all files in folder in a landscape orientation:
```
lpr -o orentation-requested=4 *
```


To prepare PDF to be printed in booklet mode:
```
pdf2ps source.pdf source.ps
psbook source.ps source_book.ps
psnup -b3mm  -m-5mm -s 0.70 -p a4 -2 source_book.ps source_booklet.ps
ps2pdf source_booklet.ps
rm source*.ps
```

Convert image to pdf:
```
img2pdf *.jpg -o out.pdf
```
