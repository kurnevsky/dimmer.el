# Recipe for converting video to animated gif using ffmpeg
# Reference: https://engineering.giphy.com/how-to-make-gifs-with-ffmpeg/

VIDEOS = dimmer-demo.webm

GIFS = $(VIDEOS:.webm=.gif)

default: $(GIFS)

clean:
	rm -f $(GIFS)

%.gif : %.webm
	ffmpeg -i $< -filter_complex "[0:v] fps=15,scale=w=640:h=-1,split [a][b];[a] palettegen [p];[b][p] paletteuse" $@


