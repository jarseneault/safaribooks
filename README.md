# safaribooks
Convert safaribooksonline ebook to epub and Kindle mobi format

# Usage
WARNING: use at your own risk.

## Installation

1. If you want Kindle mobi output, download kindlegen from Amazon and put the binary somewhere in PATH.

   If you only need epub books this step can be skipped.

2. Make sure you have Python 2 installed (Tested version Python 2.7) then run:

   `pip install safaribooks`

3. Download a book.

  `safaribooks -u USER/EMAIL -p PASSWORD -b BOOK_ID`.

   `BOOK_ID` is the id in url such as `9781617291920` in `https://www.safaribooksonline.com/library/view/real-world-machine-learning/9781617291920/kindle_split_011.html`.

   An epub and a mobi file will be generated.


## Installation with docker

This should work no matter platform you're on as no dependencies other than `docker` needs to be installed.

1. Run `docker build -t safaribooks .`

2. Run `docker run -it --rm -v $(pwd)/converted:/app/converted safaribooks -u USER/EMAIL -p PASSWORD -b BOOK_ID download` and wait for it to complete

3. The .epub and .mobi should now be in the folder `converted` of your current working directory.

## Command line usage

```
usage: safaribooks [-h] [-o OUTPUT_DIRECTORY] [-u USER] [-p PASSWORD]
                   [-b BOOK_ID]
                   {download-epub,download,convert-to-mobi} ...

Crawl Safari Books Online book content

positional arguments:
  {download-epub,download,convert-to-mobi}
    download-epub       Download as epub
    download            Download as epub, and convert to mobi
    convert-to-mobi     Convert existing epub file to mobi.

optional arguments:
  -h, --help            show this help message and exit
  -o OUTPUT_DIRECTORY, --output-directory OUTPUT_DIRECTORY
                        Directory where converted files are located / should
                        be placed
  -u USER, --user USER  Safari Books Online user / e-mail address
  -p PASSWORD, --password PASSWORD
                        Safari Books Online password
  -b BOOK_ID, --book-id BOOK_ID
                        Safari Books Online book ID
```

Create an issue if you find it does not work!
