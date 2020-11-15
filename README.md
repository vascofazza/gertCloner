# gertCloner
Raspberry Pi program to clone DPI outut to HDMI

Adapted from https://github.com/alkemir/gertCloner brings frame per second instead of frame period, arbitrary rotation [todo] and other improvements.

Now, with this little program you can clone your screen. It's not as good as two independent screens,
but hopefully this program will get the ball moving.

## Setup

To get this program on your system just download this repository and ```make```, then run ```./cloner.bin```
and you should get the same image on both screens.

## Command line options
* `-help | -h:` Displays help and flag information.
* `-displaySrc:` ID of the source display. (Default: 0)
* `-displayDst:` ID of the destination display. (Default: 5)
* `-fps:` Delay between frames in milliseconds. (Default: 15)

## How it works

This program works by taking a snapshot from the current output and setting it as the output for the
VGA display. As far as I understand, all is done on the GPU so CPU overhead should be minimal. This
program is inspired by https://github.com/tasanakorn/rpi-fbcp/ . Also, dispmanx.c was of great help
as documentation on the GPU API is... incomplete.

## Contribute

Being honest, my C skillz are non-existant so please please send any changes you would like to publish.
Also, an idea that might work is to configure the framebuffer to be as big as the two screens together,
fiddle a bit with the configuration of this program to copy only the second screen portion and then
we should be able to get the independent dual screen setup! (I think)
