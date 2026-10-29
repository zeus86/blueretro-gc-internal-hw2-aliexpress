# "iBlueControlMod" (BlueRetro) GC-internal-hw2 from [aliexpress](https://www.aliexpress.com/item/1005008130369868.html)

These are some photos from the so called "iBlueControlMod" adapter for the gamecube from aliexpress. It clearly is based on [BlueRetro](https://github.com/darthcloud/BlueRetro/) , even tough they claim it isn't, and flashing BR onto it, will damage the controller.  
**This repository uses 'git-lfs`** !

## ./img 
some images from the controller with as much components removed as feasible

## ./doc
content of the usb-stick, that came with the adapter (minus installation videos and the windows-app, because they are >100MB). However, I've included a [filelist](doc/windows-app_filelist.txt) with sha256sums from the app for reference.  

the original pdf-manual-file is unfortunately ~187MB in size. a [scaled down version](doc/NGC_iBlueControlMod_Manual_scaled.pdf) is provided instead.

`sha256sum: c9dbf2783e6adb7fca1d25daa21073453ba157ae2ce6b2ac6854793e7a6af279  NGC iBlueControlMod Manual.pdf`

## firmware

I dumped the original firmware for analasis including dumping-instructions.

Also take a look onto #2 and #3 . 2 People idependently reverse-engineered the Firmware with LLMs to find out the difference to the original BlueRetro-Firmware and built a working version of the current vanilla release based on v25.10 for this board. Thanks to @dclstn and @konsolenschatz for the effort. Use on your own risk, I haven't tested them by myself, but the code looks solid. 

## License

CC-BY-4.0
