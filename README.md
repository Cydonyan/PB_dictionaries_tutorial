# PB_dictionaries_tutorial
A generic tutorial for how to convert different dictionaries for PocketBook electronic readers

## This is not an official guide and it will not probably ever be updated!
So I apologise in advance if it did not work for you, but it has worked for me 13.11.2021

All actions were performed on Linux, however this guide should probably work for Windows too.

## What you will need

* Readiness for failure and the ability to read error messages
* Python3 and Python2 installed, and also a python-tk package
* Wine if you use linux
* [pyglossary](https://github.com/ilius/pyglossary) Universal tool for dictionary conversion, **however, does not work with all formats, make sure yours is supported for read**
* [linguae](https://linguae.stalikez.info/dwnld.php) tool, .deb package did not work for me, but you can run a cross-platform python2 version (third link)
* DictionaryConverter [new version](http://www.mobileread.com/forums/attachment.php?attachmentid=42342&d=1262456131), [old version](http://www.mobileread.com/forums/attachment.php?attachmentid=40885&d=1260265451). Do not be frightened that it is .exe, it works just fine with wine. (I used the new one but i'll leave old one too just in case)
* The dictionary that you want to convert in any appropriate format

## What to do

1. You should make an empty dict.ifo file somewhere, you will need it in just a second.
2. Go to the pyglossary directory and run `python3 main.py`. It will launch a GTK3 interface.
3. Select your dictionary as an input file and dictionary.ifo file as an output file
4. After a while, the program will generate three files: dict.ifo, dict.dic and dict.idx (you won't need the last one so it is ok if it is missing) **DO NOT CLOSE THE PROGRAM UNTIL IT WILL PRINT CONVERSION TIME, EVEN IF IT IS NOT RESPONDING**
5. Then you can close pyglossary
6. Go to linguae directory and run `python2 linguae.pyw`
7. It will launch a Tkinter GUI which will hang for a while, but then respond. 
8. Open your dict.ifo file, it will againg hang for a while
9. After that you can edit a dictionary properties (second button)
10. Now press export (the third button), choose XDXF format, and choose an output path \<path\> and an output name \<dictname\>. Also you can check "export without tabs" because pocketbook does not support it
11. After an end of the process, you can close a program, your dict.xdxf will be located at \<path\>/\<dictname\>
12. Take your dict.xdxf and copy it to the DictionaryConverter directory
13. There, assuming you dictionary language is english, run `wine converter.exe dict.xdxf eng` (look for the other supported languages in the directory)
14. Your output dict.dic file will be your converted dictionary!

## About enWikitionary example dict
Its formating sucks but i did not understand how to fix it. Feel free to commit your ideas!

## Credits

* [This article](https://zderadicka.eu/convert-dictionary-for-pocketbook-ebook-reader/) which is basically what i've wrote but less clear imo
* [pyglossary](https://github.com/ilius/pyglossary) devs, thanking them for their work
* [linguae](https://stalikez.info/) dev, thanks for him too
* DictionaryConverter dev, don't even know who is he but thanks for him
* [Yawipa](https://github.com/wswu/yawipa) developers, i took the parsed enwikitionary file from them, here is their paper that they've asked to cite:

> Computational Etymology and Word Emergence
> 
> Wu, Winston and Yarowsky, David
> 
> Proceedings of The 12th Language Resources and Evaluation Conference
> 
> may 2020
> 
> Marseille, France
> 
> European Language Resources Association
> 
> https://www.aclweb.org/anthology/2020.lrec-1.397
>

Finally, sorry for the bad english, i am russian. Hope yoou've found that helpful!
