# osu-in-termux
How to do osu in termux Maybe you can do it on Raspberry Pi.


I pasted the translation results directly from Deepl.
Sorry.

# how to do it

https://qiita.com/karuakun/items/c8439d0aadb2e798cf08
https://www.reddit.com/r/termux/comments/r9jsvv/comment/ho59bvd/?utm_source=share&utm_medium=web2x&context=3
Put in a proot that runs dotnet as a reference here.

Then download osu!lazer (https://github.com/ppy/osu) and build it
Download some more libraries as we are still missing some.

https://github.com/veldrid/veldrid-spirv
This is a pain in the ass to build, so I'll leave the binaries here
https://github.com/shiumano/osu-in-termux/releases/download/untagged-f391e7a33328bf337f6c/libveldrid-spirv.so
Put this in /usr/lib

https://aur.archlinux.org/packages/libbass
https://aur.archlinux.org/packages/libbassmix
https://aur.archlinux.org/packages/libbass_fx

The great AUR has pre-built binaries of these three, so be thankful to use them!
You'll find the zip at the bottom of the Package Details box.
Unzip it and put the one in aarch64 into /usr/lib.

You should be able to start it now.

It's better to use virgl if you can.
https://github.com/xDoge26/Proot-Setup#41-virgl-es-recommended
Please refer to here to install it

# Bugs and problems that occur
Slow (10fps with llvmpipe, 30~40fps with virgl)
Sound is very off.
　Offset should have been -100ms.
　Sound is off by +200ms, so volume of sound effect should be 0.
Some virgl moments.
　Pie chart is rotten.
　The music information is white.
　No triangles effect.
The background video doesn't play.
