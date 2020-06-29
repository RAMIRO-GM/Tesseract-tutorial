# Tesseract-tutorial
## Tesseract OCR tutorial in python. 
### This tutorial was obtained by this excellent post: [Further reading](https://nanonets.com/blog/ocr-with-tesseract/)
## In this tutorial you will be able to:
* Use python Tesseract wrapper pytesseract and extract text from images.
* Apply some image preprocessing steps before applying the OCR.
* Get the boxes of all the characteres identified by Tesseract in an image.
* Get the boxes of all the complete words identified by Tesseract in an image.
* Text template matching: Take the example of trying to find where a date is in an image.
* Whitelisting characters: If you only want to detect certain characters from the given image and ignore the rest. You can specify your whitelist of characters 
* Blacklisting characters: If you are sure some characters or expressions definitely will not turn up in your text, you can balcklist those characters.

# Downloading Tesseract
Follow this excellent video tutorial to install Tesseract (windows): [Download Tesseract on windonws](https://www.youtube.com/watch?v=Rb93uLXiTwA)
or download the exe file and run it [Donwload Tesseract](https://github.com/UB-Mannheim/tesseract/wiki)
# Running Tesseract with CLI
Call the Tesseract engine on the image with image_path and convert image to text, written line by line in the command prompt by typing the following:
``` bash
 $ tesseract image_path stdout
```
To write the output text in a file:
``` bash

$ tesseract image_path text_result.txt
```

To specify the language model name, write language shortcut after -l flag, by default it takes English language:
``` bash
$ tesseract image_path text_result.txt -l eng
```

By default, Tesseract expects a page of text when it segments an image. If you're just seeking to OCR a small region, try a different segmentation mode, using the --psm argument. There are 14 modes available which can be found here. By default, Tesseract fully automates the page segmentation but does not perform orientation and script detection. To specify the parameter, type the following:
``` bash
$ tesseract image_path text_result.txt -l eng --psm 6
``` 
There is also one more important argument, OCR engine mode (oem). Tesseract 4 has two OCR engines — Legacy Tesseract engine and LSTM engine. There are four modes of operation chosen using the --oem option.
* 0    Legacy engine only.
* 1    Neural nets LSTM engine only.
* 2    Legacy + LSTM engines.
* 3    Default, based on what is available.
