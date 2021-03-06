# ImageMagick


### Create an empty image
convert -size 800x800 xc:white out.png

### Replace color - white to beige, allow 10% fuzz
`convert s1.png -fuzz 10% -fill "#F2F1DD" -opaque "#FFFFF" s2.png`

### Draw a transparent rectangle on a photo
`convert in.jpg -fill none -stroke red -strokewidth 3 -draw "rectangle 10,10,200,300" out.jpg `

### Compress PDF
	`convert input.pdf -compress Zip output.pdf`

### Invert image
convert in.png -negate out.png

### List installed fonts
`convert -list font`

### Create outlined text
`convert -size 320x100 xc:lightblue -font Bookman-Light -pointsize 72 \
            -draw "fill black text 27,67 'Geekery' \
                              text 25,68 'Geekery' \
                              text 23,67 'Geekery' \
                              text 22,65 'Geekery' \
                              text 23,63 'Geekery' \
                              text 25,62 'Geekery' \
                              text 27,63 'Geekery' \
                              text 28,65 'Geekery' \
                   fill white text 25,65 'Geekery' " \
           font_outlined_12.jpg`

### Polaroid effect
convert -caption "my text" ext.jpg -gravity center            -background black +polaroid polaroid.png
#### smaller ones
convert $d -geometry 200x200 -gravity center -background black +polaroid polaroid.png


### Create Animated Image

convert -delay 20 -loop 0 frame*gif animated.gif

### Convert animated Image into Frames

convert -coalesce brocoli.gif out%05d.pgm

### Remove transparency

convert -flatten -background white in.png out.png

### Add Watermark Text to Image

convert bla.png -pointsize 50 -font Arial -fill "rgba(0,0,0,0.4)" -gravity center -annotate +0+0 "Geekery" bla2.png

### OSX imagesnap (with brew)

#### take one
imagesnap -w 1 snapshot.png

#### take one every second
imagesnap -t 1 -w 1

#### Create fixed size thumbnails for all pics and put them in a 'thumbs' subdirectory

mogrify -resize 150x150 -background white -gravity center -extent 80x80 -format jpg -quality 75 -path thumbs *.jpg



