# KDE Service Menus for Image File Processing

Enhance your image file workflows with KDE service menus, tailored for efficient processing.

---

## Requirements

To use these service menus, ensure the following are installed:

- [KDE](https://www.kde.org/)
- [libnotify](https://github.com/GNOME/libnotify)
- [ImageMagick](https://imagemagick.org/index.php)
- [ExifTool](https://exiftool.org/)
- [JPEG XL reference implementation](https://github.com/libjxl/libjxl)
- [OptiPNG](http://optipng.sourceforge.net/)
- [pngquant](https://pngquant.org/)
- [Jpegoptim](https://github.com/tjko/jpegoptim)

---

## Installation (Plasma 6)

### Install Dependencies (Arch Linux)

Use the following command to install the required tools:

```bash
sudo pacman -S imagemagick perl-image-exiftool libjxl optipng pngquant jpegotim qt6-tools
```

### System-Wide Installation

Copy the necessary files to their respective system directories:

```bash
sudo cp servicemenus/* /usr/share/kio/servicemenus/
sudo cp bin/imagetools-kdialog /usr/local/bin/
```

### Per-User Installation

For a user-specific setup, copy the files as follows:

```bash
cp servicemenus/* ~/.local/share/kio/servicemenus/
cp bin/imagetools-kdialog ~/.local/bin/
```

Ensure `~/.local/bin` is included in your `$PATH` environment variable.  
Additionally, make the `.desktop` files executable:

```bash
chmod +x ~/.local/share/kio/servicemenus/image-tools*.desktop
```

Finally, restart your Plasma session or run:

```bash
kbuildsycoca6
```

---

## Uninstallation

### System-Wide Uninstallation

Remove the installed files:

```bash
sudo rm /usr/share/kio/servicemenus/image-tools*.desktop
sudo rm /usr/local/bin/imagetools-kdialog
```

### Per-User Uninstallation

Delete the corresponding files:

```bash
rm ~/.local/share/kio/servicemenus/image-tools*.desktop
rm ~/.local/bin/imagetools-kdialog
```

---

## Resetting Suppressed Overwrite Dialog Decisions

To reset the "overwrite dialog" decision, delete the configuration file:

```bash
rm ~/.config/servicemenus-imagetools
```

---

## What Does "Prepare for Publishing" (JPEG) Do?

This function applies the following steps:

1. Scale the longer side of the image to 1920px (Full HD).
2. Recompress the image with 70% quality and optimize the file size.
3. Remove all non-essential metadata (only technical data is retained).

This process ensures the images are more suitable for tasks like emailing or uploading to untrusted systems.

---

## Contributing

We welcome contributions! Please follow these guidelines:

- For major changes, open an issue first to discuss your ideas.
- Ensure tests are updated as needed.

Pull requests are encouraged and appreciated!

---

## License

This project is licensed under [GPL-3.0+](https://www.gnu.org/licenses/gpl-3.0.html).
