# docker-libreoffice-pdf-cli

> Convert any doc to pdf without installing LibreOffice and its dependencies

## Features

* Doesn't clutter your system with shit-ton of LibreOffice dependencies!
* UNIX way - feed in `stdin` and get from `stdout`
* So no docker volumes mounting needed
* `--rm` arg ensures container is removed after converting. Doesn't clutter your Docker
* Easy removing: `docker rmi vladgolubev/libreoffice-pdf-cli && rm ~/bin/topdf`

## Install

This will just create a convenient shorthand command:

```bash
$ echo "docker run --rm -i vladgolubev/libreoffice-pdf-cli" > ~/bin/topdf && chmod +x ~/bin/topdf
```

## Usage

```bash
$ cat Document.docx | topdf > Document.pdf
```

Optionally, if you have `pdftk` installed, you can for example cut 1st page:

```
$ cat Document.docx | topdf | pdftk cat 1 > Document.pdf
```
