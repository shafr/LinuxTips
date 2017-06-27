#Youtube download whole channel
```bash
nohup \
youtube-dl \
--no-progress \
-o '%(uploader)s/%(playlist)s/%(playlist_index)s - %(title)s.%(ext)s' \
https://www.youtube.com/channel/<CHANNEL_ID>/playlists \
&
```