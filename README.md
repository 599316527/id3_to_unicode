ID3 to unicode converter
==============

Converter for mp3 tags into unicode in utf8 format.

Python code is copied from https://code.google.com/p/id3-to-unicode/. Slight adjustment are made to make it work with current EyeD3 API.

It worked for me at least once. Most likely it's quite buggy after my quick changes. Feel free to fork and update it for your needs.

## Usage

Install dependencies first.

```bash
pip install chardet eyed3
```

**Tip** for Chinese:

Use the mirror `-i https://pypi.mirrors.ustc.edu.cn/simple/` instead for your poor international internet connection speed. *How sweet I am!*

Then run it.

```bash
python id3_to_unicode.py [options] [MP3Path...]
```

Options:

* -h, --help

    show this help message and exit

* -r, --recursive

    search recursively

* -u, --update

    update mp3 files

* -o, --overwrite

    overwrite tags from Artist/Album/Title directory structure

* -R, --rename

    rename file as well

* -f, --force

    treat files as mp3

* -e ENCODING, --encoding ENCODING

    always assume this encoding

* --no-title-prefix

    remove prefix number in title

    Eg: "02. We are never ever..." -> "We are never ever..."

Original readme:
<pre>
    The encoding statistics are calculated in every directory and easy
    cases are processed automatically. However, if statistics show
    there are several potential candidates for the proper encoding,
    the selection options/probabilities are given to the user.

    Wrong encoding choice usually results in encoding errors, therefore,
    please, use 'dry run' mode until you figure out the proper encoding,
    and only then use '-u' option to actually modify your files.

    Separate directories may have different iD3 tags encodings, but
    all files within the same directory are supposed to share the same
    encoding. Usually, every album is kept in the separate directory and
    this does not constitute any problems. However, if you have 2000+ mp3
    files with Chinese, Hebrew and Cyrillic tags in one large directory,
    they'd better be sorted beforehand.

    Missing iD3 tags are recreated from the file and/or directory names.
    For that purpose your music collection is supposed to be sorted by
    Artist/Album in separate directories:

        /home/user/Music/Artist/Album 2003/01 Song Title.mp3

    However, if all .mp3 files are already tagged, the directory
    structure is irrelevant and can be anything you like.

    Please, backup your .mp3 files before processing!

    Copyright(c) 2010-2012, lenik terenin
</pre>
