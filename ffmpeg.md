### Generate still images from video - 1 snapshot per second

ffmpeg -i funfair.mp4 -vf fps=1 out%d.png

### capture livestream and save into 10 second segments

ffmpeg -i rtsp://mpv.cdn3.bigCDN.com:554/bigCDN/definst/mp4:bigbuckbunnyiphone_400.mp4 -c copy -map 0 -f segment -segment_time 10 -segment_format mp4 "capture-%03d.mp4
