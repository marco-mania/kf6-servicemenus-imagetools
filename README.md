# KDE service menus for image file processing

KDE service menus for image file processing.

* Special functions for JPEG and PNG files

Originally derived from [KDE 5 Service Menu ReImage v2.5](https://www.egregorion.net/),
Copyright (C) 2018-2019 Giuseppe Benigno <giuseppe.benigno@gmail.com>, GPL-3.0+

## Requirements

* [KDE](https://www.kde.org/)
* [ImageMagick](https://imagemagick.org/index.php)
* [ExifTool](https://exiftool.org/)
* [OptiPNG](http://optipng.sourceforge.net/)

## Installation (Plasma 6)

Install the requirements (Arch Linux):

    sudo pacman -S imagemagick perl-image-exiftool optipng qt5-tools

To install system wide:

    sudo cp servicemenus/* /usr/share/kio/servicemenus/
    sudo cp bin/imagetools-kdialog /usr/local/bin/

Per user installation:

    cp servicemenus/* ~/.local/share/kio/servicemenus/
    cp bin/imagetools-kdialog ~/.local/bin/

In that case the directory `~/.local/bin` has to be be placed in the search path
environment variable `$PATH`.
E.g. for a Fish shell you can simply call `fish_add_path ~/.local/bin`.
Also make sure your .desktop files are execuatable
`chmod +x ~/.local/share/kio/servicemenus/image-tools*.desktop`.

Finally you need to restart your plasma session or call:

    kbuildsycoca6

## Uninstall

System wide installation:

    sudo rm /usr/share/kio/servicemenus/image-tools*.desktop
    sudo rm /usr/local/bin/imagetools-kdialog

Per user installation:

    rm ~/.local/share/kio/servicemenus/image-tools*.desktop
    rm ~/.local/bin/imagetools-kdialog

## Contributing

Pull requests are welcome. For major changes, please open an issue first to
discuss what you would like to change.

Please make sure to update tests as appropriate.

## License

[GPL-3.0+](https://www.gnu.org/licenses/gpl-3.0.html)
