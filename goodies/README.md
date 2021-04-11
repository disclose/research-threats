# Goodies folder

This folder is named in the style of [xfce4-goodies](https://goodies.xfce.org/), [debian-goodies](https://packages.debian.org/stretch/debian-goodies), etc.

# Please sanitize Personally Identifiable Information (PII) from PDF, PNG, JPG files.

In the interest of Security Researcher safety, and prevent you from doxxing yourself, you may want to remove all EXIF data from uploads.

## If you accidentally upload EXIF data containing documents

If you have accidentally uploaded documents to your branch with [Personally identifiable information](https://en.wikipedia.org/wiki/Personal_data) (PII), you have a some time to remove that content from GitHub, usually before it is archived.

If you have any issues files that you do not wish to have in the repository, drop a quick line at [https://disclose.io/contact/](https://disclose.io/contact/) and collaborators will do their best to remove it (e.g. `git force push`).


### Install [ExifTool](https://github.com/exiftool/exiftool)
```bash
# ubuntu, debian, pop
sudo apt update -y
sudo apt install exiftool -y

# centos, fedora, rhel, rocky
sudo yum update -y
sudo yum install epel-release -y
sudo yum install perl-Image-ExifTool -y

# arch, manjaro
sudo pacman -Syu perl-image-exiftool
```

`exiftool` with the `-all` option set to nothing will remove all EXIF data.

### These are all the same and will remove all EXIF data from your uploads.

```bash
exiftool -all='' document.pdf
exiftool -all= image.png
exiftool -all= image.jpg
exiftool -all= *.png
```

### Verify the exif data has been removed:
```bash
exiftool document.pdf
```
### Example output:

```console
[user@hostname goodies]$ exiftool "Document.pdf" 
ExifTool Version Number         : 12.16
File Name                       : Document.pdf
Directory                       : .
File Size                       : 182 KiB
File Modification Date/Time     : 2021:04:11 08:16:26+00:00
File Access Date/Time           : 2021:04:11 08:16:27+00:00
File Inode Change Date/Time     : 2021:04:11 08:16:26+00:00
File Permissions                : rw-r--r--
File Type                       : PDF
File Type Extension             : pdf
MIME Type                       : application/pdf
PDF Version                     : 1.5
Linearized                      : No
Language                        : en
Page Count                      : 1
```