Use this command to compress gif files

> ffmpeg -i input -filter_complex "[0:v] fps=15,scale=-1:360,mpdecimate,split [a][b];[a] palettegen=max_colors=64 [p];[b][p] paletteuse=dither=bayer:bayer_scale=5" output.gif