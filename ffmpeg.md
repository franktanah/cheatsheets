### Generate still images from video - 1 snapshot per second

ffmpeg -i funfair.mp4 -vf fps=1 out%d.png

### capture livestream and save into 10 second segments

ffmpeg -i rtsp://mpv.cdn3.bigCDN.com:554/bigCDN/definst/mp4:bigbuckbunnyiphone_400.mp4 -c copy -map 0 -f segment -segment_time 10 -segment_format mp4 "capture-%03d.mp4"

### slide video into skills

##### 5 frames per second
ffmpeg -i video.mp4 -vf fps=5 still_%03d.png

### OSX FaceTime Camera

#### get devices
ffmpeg -f avfoundation -list_devices true -i ""

#### then record the first device to file

ffmpeg -r 30 -f avfoundation -i "0" -y out.mov

#### capture camera into 10 second fragments

ffmpeg -r 30 -f avfoundation -i "0" -f segment -segment_time 10 -segment_format mp4 "capture-%03d.mp4

#### record 5 seconds

ffmpeg -r 30 -f avfoundation -i "0" -pix_fmt yuv420p -r 25 -t 5 out.mov

#### create RTP stream from device

( ffmpeg -r 30 -f avfoundation -i "0" -sdp_file stream.sdp -f rtp rtp://0.0.0.0:12345 ) 

ffmpeg -framerate 30 -f avfoundation -i "default" -vcodec libx264 -tune zerolatency -vf scale=1920:1080 -b 900k -sdp_file stream.sdp -f rtp "rtp://127.0.0.1:5600"

#### take a pic using Facetime camera

ffmpeg -r 30 -f avfoundation -i "0" -frames 1 s.png


### Start an RTP server locally

ffmpeg -re -f lavfi -i aevalsrc="sin(400*2*PI*t)" -ar 8000 -f mulaw -f rtp rtp://127.0.0.1:1234

### Droidcam
Droicam get one frame
http://192.168.1.106:4747/cam/1/frame.jpg

Droidcam raw image stream
http://192.168.1.106:4747/mjpegfeed?640x480

Take one still image every second
ffmpeg -r 30 -i http://192.168.1.106:4747/mjpegfeed?640x480 -vf fps=1 out%d.png

##### ffmpeg HLS MacOS

ffmpeg -re -i $ffile -vf "scale=-2:$320" -hls_flags delete_segments o.m3u8 >/dev/null 2>/dev/null

`<video width="600" height="400" controls>
<source src="http://localhost/o.m3u8" type='application/x-mpegURL' / >
</video>`