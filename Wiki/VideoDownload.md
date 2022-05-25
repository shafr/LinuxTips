Download .ts files & merge them into mp4 file:

```bash
#!/bin/bash

for INDEX in {0..100} #you'll get that from m3u file
do
	END_STR=$(printf %05d $INDEX)
	NEW_STR="<start>_${END_STR}.ts"
	
	wget -nc $NEW_STR
done

CHAPTER=8

for i in `\ls *.ts | sort -V`; do echo "file '$i'"; done >> mylist.txt
ffmpeg -f concat -i mylist.txt -c copy -bsf:a aac_adtstoasc chapter_${CHAPTER}.mp4

mkdir ${CHAPTER}
mv *.ts ${CHAPTER}/
mv *.mp4 ${CHAPTER}/
rm -rf mylist.txt

#vlc ${CHAPTER}/chapter_${CHAPTER}.mp4
```
