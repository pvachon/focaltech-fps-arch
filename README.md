# Driver for HOLTEK FocalTech 0752
This is an Arch Linux package for the HOLTEK FocalTech 0752 fingerprint sensor,
as is used in the GPD Pocket 4. It is a gigantic proprietary blob of code that
runs natively on the host CPU. Quick analysis shows that this blob contains a
userspace USB driver, a feature extractor, template matcher and other sundries
within. It replaces the normal backing libraries for fprintd wholesale.

## Building and Installing
A simple `makepkg -s` in the directory containing the PKGBUILD file should be
enough. Then use `pacman -U` to install the resulting package file.

## Prior Art
Based on some work in a Github gist I found [here](https://gist.github.com/Mnkai/b755df1452c38eaf9af12636844e61da/), but with cleanups.

## License
Who knows?
