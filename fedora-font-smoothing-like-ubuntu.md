## Ubuntu like font smoothing in Fedora

By default, fedora's font smoothing is not as good as Ubuntu. Even when made the necessary symlinks in `/etc/fonts/conf.d` directory and changing the hinting and antialiasing option, this remains problematic. But fortunately there is a fix I found in [this blog post.](https://digitz.org/blog/fix-ugly-fonts-in-fedora/)

#### Solution

The solution consist of two steps.

1. Install `freetype-freeworld` package. Just enable for rpmfusion repository and you'll get it.
2. Then make a fontconfig `.conf` file and store it in either `~/.config/fontconfig/` directory or `/etc/fonts/conf.d` directory. The content of the file should be like this. Save the file and reboot.

```xml
<?xml version="1.0"?>
<!DOCTYPE fontconfig SYSTEM "fonts.dtd">
<fontconfig>
  <match target="pattern">
    <edit name="dpi" mode="assign">96</edit>
  </match>
  <match target="font">
    <edit mode="assign" name="antialias" >
      <bool>true</bool>
    </edit>
  </match>
  <match target="font">
    <edit mode="assign" name="hinting" >
      <bool>true</bool>
    </edit>
  </match>
  <match target="font">
    <edit mode="assign" name="hintstyle" >
      <const>hintslight</const>
    </edit>
  </match>
  <match target="font">
    <edit mode="assign" name="rgba" >
      <const>rgb</const>
    </edit>
  </match>
  <match target="font">
    <edit mode="assign" name="lcdfilter">
      <const>lcddefault</const>
    </edit>
  </match>
</fontconfig>
```



